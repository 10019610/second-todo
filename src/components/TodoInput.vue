<template>
  <div class="inputBox shadow">
    <input
      type="text"
      v-model="newTodoItem"
      v-on:keyup.enter="addTodo"
      placeholder="To do"
      style="text-align: center"
    />
    <span class="addContainer" v-on:click="addTodo">
      <i class="bi bi-calendar-plus addBtn"></i>
            <!-- <i class="fas fa-calendar-plus addBtn"></i> -->
    </span>

    <TodoModal v-if="showModal" @close="showModal = false">     
        <h3 slot="header">
          경고!
          <i class="closeModalBtn bi bi-x-square" @click="showModal = false"></i>
        </h3>
        <div slot="body">
          아무것도 입력하지 않았어요.
        </div>
        <!-- <h4 slot="footer"> -->
          <!-- copy right -->
        <!-- </h4> -->


        바디: 무언가를 입력하세요
        푸터: copy right
      </TodoModal>
  </div>
</template>

<script>
import TodoModal from './common/TodoModal.vue'

export default {
  data() {
    return {
      newTodoItem: "",
      showModal: false
    };
  },
  methods: {
    addTodo() {
      if (this.newTodoItem !== "") {
        // this.$emit('addTodoItem',this.newTodoItem)
        this.$store.commit('addOneItem', this.newTodoItem)
        this.clearInput();
      } else{
        this.showModal = !this.showModal;
      }
      
    },
    clearInput() {
      this.newTodoItem = "";
    }
  },
  components: {
    TodoModal
  },
};
</script>

<style scoped>
input:focus {
  outline: none;
}
.inputBox {
  background: white;
  height: 50px;
  line-height: 50px;
  border-radius: 5px;
}
.inputBox input {
  height: 40px;
  width: 80%;
  border-style: none;
  font-size: 0.9rem;
}
.addContainer {
  float: right;
  background: linear-gradient(to right, #6478f8, #8763fb);
  display: block;
  width: 3rem;
  border-radius: 0 5px 5px 0;
}
.addBtn {
  color: white;
  width: 50px;
  vertical-align: middle;
}
.closeModalBtn {
  color: #42b983;
}
</style>
