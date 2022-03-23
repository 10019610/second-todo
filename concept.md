# network status

## http 상태 코드임 

### 100-199 Information responses
### 200-299 Successful responses  아까 200이 떴으니 성공적으로 네트워크 연결된듯
### 300-399 Redirection message
### 400-499 Client error responses
### 500-599 Server error responses


# requestBody

## 클라이언트에서 서버로 통신하는 메시지가 request(요청)메시지
## 서버에서 클라이언트로 통신하는 메시지를 response(응답)메시지 라고함
## 비동기 통신을 하기 위해서 클라이언트에서 서버로  request를 보낼때, 
## 본문에 데이터를 담아서 보내야하고, 서버에서 클라이언트로 응답을 보낼때에도 본문에 데이터를 담아서 보내야한다. 이때의 이 본문이 body임

## 클라이언트가 보내는 HTTP 요청 body를 java object로 변환하여 매핑된 메소드 파라미터로 전달해줌.

# Modelattribute 
## 객체를 만들어 입력받은 값을 바로 객체 안에 담고 객체 그 자체를 넘길수 있는 어노테이션..

## @ModelAttribute("파라미터명")
