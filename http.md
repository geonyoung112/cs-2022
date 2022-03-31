<!-- Heading -->

# HTTP란 무엇일까? 👀

## HTTP란?

<!-- Text attributes-->

- [_HTTP_](https://ko.wikipedia.org/wiki/HTTP) 는 _Hyper Text Trensfer Protocol_ 의 약자로 하이퍼텍스트(Hyper)를 전송하는 프로토콜이다.
  HTTP는 1990년대 초에 설계되었으며 거듭하여 진화해온 확장 가능한 프로토콜이다. HTTP는 애플리케이션 계층(OSI 7계층)의 프로토콜로, 신뢰 가능한 전송 프로토콜이라면 이론상으로는 무엇이든 사용할 수 있으나 TCP 혹은 암호화된 TCP연결인 TLS를 통해 전송된다.

  > _💻 월드와이드웹의 약자인 WWW_ 는 유럽입자물리연구소의 연구원인 팀 버너스 리가 1989년에 제안하여 개발된 정보 공유 방안이다. WWW는 전 세계의 인터넷 기반에서 하이퍼텍스트(Hyper) 기반의 정보를 누구나 쉽게 공유할 수 있는 정보 구축 방법으로 하이퍼 텍스트 자료들은 HTML이라는 언어를 통해 표현되며, 이러한 문서들은 HTTP라는 통신 프로토콜을 사용하여 전송된다.

  > _📁 하이퍼텍스트_ 는 정보를 서로 연결하는 하이퍼링크에의하여 구성된 정보를 말한다. 하이퍼텍스트를 구성하는 정보는 문자, 그림, 동영상, 음악, 파일 등의 멀티미디어 정보가 있으며, 이 멀티미디어 정보를 강조한 용어가 _📁 하이퍼미디어(Hypermedia)_ 다. 이러한 하이퍼텍스트의 무한한 정보의 연결 방안과 인터넷이라는 지역성의 파괴의 결합인 WWW는 웹 브라우저의 개발과 함께 전 세계의 사람을 정보의 바다로 빠져들게 했다.

즉, 팀 버너스 리와 그의 팀은 HTML을 전송하기 위해 HTTP라는 프로토콜을 발명했었다.

---

## 🔁 HTTP 동작

HTTP는 클라이언트와 서버 사이에 이루어지는 *요청/응답 프로토콜*이다.

자세히 설명하자면, 클라이언트, 사용자가 브라우저를 통해서 어떠한 서비스를 url을 통하거나 다른 것을 통해서 _* 요청(request)을 하면 서버에서는 해당 요청사항에 맞는 결과를 찾아서 사용자에게 응답(response)*_ 하는 형태로 동작한다.

![image desciption](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FdcUnst%2FbtqWXaFbg2p%2F86WwcX7OsOvnkoO71T0RbK%2Fimg.png)

> <span style="color:green">클라이언트

서버에게 요청을 보내는 리소스 사용자

ex) 웹 브라우저, 모바일 애플리케이션, IoT 등

> <span style="color:purple">서버

클라이언트에게 요청에 대한 응답을 제공하는 리소스 관리자

- 예를 들어 웹 브라우저에서 HTTP 프로토콜로 서버에 HTML이나 그림과 같은 리소스 정보를 요청하면, 서버는 이 요청에 응답하여 필요한 정보를 해당 브라우저로 전송하게 된다. 전달받은 정보는 브라우저에서 해석과정을 거쳐 사용자가 원하는 결과창으로 화면에 보여준다. 이러한 교류는 HTTP 프로토콜을 이용하여 발생하게 된다.

> 또한, HTML 문서만이 HTTP 통신을 위한 유일한 정보 문서는 아니다.
> Plain text로 부터 JSON 데이터 및 XML과 같은 형태의 정보도 주고 받을 수 있으며, 보통은 클라이언트가 어떤 정보를 HTML 형태로 받고 싶은지, JSON 형태로 받고 싶은지 명시해주는 경우가 많다.

---

## ✔️ HTTP의 특징

![image desciption](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FwGe0D%2FbtqWxfaBEsr%2FlSsKYP5jHLEbV2gOeKHVm0%2Fimg.png)

1. _*HTTP는 간단하다*_ : HTTP는 사람이 읽을 수 있도록 간단하게 고안되었다.
2. _*확장 가능하다*_ : 클라이언트와 서버가 새로운 헤더의 시맨틱에 대해서만 합의한다면, 언제든지 새로운 기능을 추가할 수 있다.
3. _*무상태(Stateless)*_ : HTTP는 상태를 저장하지 않는다. 즉, 통신간의 연결 상태 처리나, 정보를 저장할 필요가 없기 때문에 서버 디자인이 간단해진다는 장점이 있다. 만약 저장이 필요한 경우에는 쿠키나 세션을 활용해 정보를 저장할 수 있다
4. _*비연결성(Connectionless)*_ : HTTP는 클라이언트와 서버가 한 번 연결을 맺은 후, 클라이언트의 요청에 대해 서버가 응답을 마치면 맺었던 연결을 끊어버리는 성질을 말한다. 이러한 특징의 장점은 컴퓨터마다 매번 연결을 유지할 필요가 없기 때문에 리소스를 줄일 수 있어 더 많은 연결을 그때그때 수행할 수 있다는 장점이 있다.

---

## HTTP의 흐름

1. TCP 연결을 연다.
2. HTTP 메시지를 전송한다.
3. 서버에 의해 전송된 응답을 읽는다.
4. 연결을 닫거나 다른 요청들을 위해 재사용한다.

> 클라이언트와 서버 사이의 소통은 데이터 스트림과 대조적으로 평문(ASCII) 메시지로 이루어진다.

---

## 요청(Request)

![image desciption](https://kyun2da.dev/static/d2fb56022283926751de8706c41d2736/61c63/http_request.png)

1. http 메서드
2. 리소스의 경로
3. http 프로토콜 버전
4. 헤더
5. body

클라이언트(브라우저)가 서버에게 연락하는 것을 요청이라고 하며, 요청을 보낼때에는 요청에 대한 정보를 담아 서버로 보내게 된다.

> 요청의 종류(Request Method)

1. GET : 자료를 요청할 때 사용
2. POST : 자료의 생성을 요청할 때 사용
3. PUT : 자료의 수정을 요청할 때 사용
4. DELETE : 자료의 삭제를 요청할 때 사용

💬 _요청 예시 (참고: 사진)_

<span style="color:lightblue">GET http://www.github.com HTTP/1.1 User-Agent: Mozilla/5.0(Windows Nt 10.0Won 64; x64)....
Upgrad-Insecure-Requests: 1

요청의 첫 줄에는 주소와,http 버전이 들어온다.
두번째부터 헤더로 요청에 대한 정보를 담고있다.
이어 헤더에서 한 줄 띄고 본문이 시작된다. 본문은 요청할 때 함께 보낸 데이터를 담는 부분이다.

---

## 응답(Response)

서버가 요청(Request)에 대해서 답변을 클라이언트에게 보내는 것을 뜻한다.

![image desciption](https://kyun2da.dev/static/94e095a3fcf89fd3e3fd792d5de89ba2/c8e86/http_response.png)

1. http 프로토콜 버전
2. 상태 코드
3. 상태 메시지
4. http 헤더
5. body

💬 _응답 예시 (참고: 사진)_

<span style="color:lightblue">HTTP/1.1 200 OK ---> 이는 버전, 상태코드 상태메시지 200 ---> 성공적인 요청이라는 의미

> 상태 코드(Status Code):
> 상태 코드에는 굉장히 많은 종류가 있다. 세 자리 숫자로 이루어져 있으며, 크게 다섯 부류로 나눌 수 있다.

- 1○○ (조건부 응답) : 요청을 받았으며 작업을 계속한다.
- 2○○ (성공) : 클라이언트가 요청한 동작을 수신하여 이해했고 승인했으며 성공적으로 처리했음을 가리킨다.
- 3○○ (리다이렉션 완료) : 클라이언트는 요청을 마치기 위한 추가 동작을 취해야 한다.
- 4○○ (요청 오류) : 클라이언트에 오류가 있음을 나타낸다.
- 5○○ (서버 오류) : 서버가 요청을 수행하지 못했음을 나타낸다.

<span style="color:lightblue">Connetcion: keep-alive ---> 헤더, 응답에 대한 정보를 담고 있다.

<span style="color:lightblue">Content-Encoding: gzip ---> 본문, 응답 메시지에는 오청한 데이터를 담아 보내준다.

<span style="color:lightblue"> Content-length: 35653

<span style="color:lightblue">content-Type: text/html

이처럼 응답 메시지에 HTML이 담겨 있고, html을 받아 브라우저가 화면에 렌더링한다.

> _렌더링_ : 컴퓨터 프로그램을 사용하여 모델또는 이들을 모아놓은 장면인 씬 파일(scene file)로부터 영상을 만들어내는 과정을 말한다.

이렇게 HTTP란 무엇이고 HTTP의 특징, 자세한 전송 흐름까지 공부했습니다.🤩

---

## ⚠️ 참고문서

- https://velog.io/@surim014/HTTP%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80
- https://lipcoder.tistory.com/485
- https://kunsae.tistory.com/6
