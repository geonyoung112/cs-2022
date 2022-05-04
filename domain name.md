# Domain Name

## 도메린 네임이란?

1. 도메인 네임이란 IP 주소를 문자로 알아보기 쉽게 만든 인터넷 상의 주소

2. 도메인 네임의 구조는 다음과 같다.

![image description](https://velog.velcdn.com/images%2Fm-vault%2Fpost%2Faa47ab6d-b47e-4150-b23d-4feb79d20924%2F1.png)

우측에서 좌측으로 읽으며, Root - TLD - SLD - SUB(도메인 이름) 순이다.
www는 도메인 네임에 포함되지 않는 ‘호스트명’ 이다.

> 도메인 네임은 넓은 의미로는 네트워크상에서 컴퓨터를 식별하는 호스트명을 가리키며, 좁은 의미에서는 도메인 레지스트리에게서 등록된 이름을 의미한다. 이를 통틀어서 ‘웹 주소’라고 부르는 경우도 있다.
> 출처: 위키백과

## 도메인 네임의 구조

![image description](https://velog.velcdn.com/images%2Fm-vault%2Fpost%2Faa47ab6d-b47e-4150-b23d-4feb79d20924%2F1.png)

- dns 내용에서 말했듯이, 각 DNS 서버들은 자신의 직속 하위 파트에 대한 정보를 알고 있어야 한다. Root 는 TLD에 대한 정보를, TLD는 SLD에 대한 정보를 아는 식으로 구성되어 있다.

1. Root
   가장 최상위에 위치해있다.
   실제로 주소엔 . 이 있으나, 생략된 형태로 사용해도 무방하다.

2. TLD (Top-Level Domain, 최상위 도메인)
   도메인 레벨 중에 가장 높은 단계에 있는 도메인으로, 도메인의 목적, 종류, 국가를 나타낸다.
   .com , .org , .net 등이 일반적이며, .kr .us 등 특정 국가를 나타내기도 한다.

3. SLD (Second-Level Domain, 차상위 도메인)
   ‘www.google.co.kr’ 처럼 SLD가 존재하는 경우도 있고, ‘www.naver.com’ 처럼 SLD가 존재하지 않고 TLD에서 바로 도메인 이름으로 건너뛰는 경우도 있다.

   > co : 영리 목적의 단체, 기업체
   > go : 정부 기관 등 도메인의 성격을 나타낸다.

4. SUB (도메인 이름)
   임의로 지정할 수 있는 사이트의 이름.
   → google, naver, daum 등이 도메인 이름 부분

5. www
   world wide web의 약자로, 도메인 네임에 포함되지 않는 ‘호스트명’이다.

> SLD은 쓸 수도, 생략할 수도 있기 때문에 도메인 구조를 단계로 나눴을 때,
> ‘www.google.co.kr’ 처럼 3단계 구조일수도 있고
> ‘www.naver.com’ 처럼 2단계 구조가 될 수도 있다
