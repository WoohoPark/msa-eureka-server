Spring MSA 환경 세팅하기

![img1 daumcdn](https://user-images.githubusercontent.com/24665763/197341827-3a26cb17-4d19-4d54-b4a8-2d43beff7f7f.png)


#STEP1

Eureka는 무엇인가?

클라우드 환경의 다수의 서비스(예: API 서버)들의 로드 밸런싱 및 장애 조치 목적을 가진 미들웨어서버이다.
Eureka는 이러한 미들웨어 기능을 하기 위해 각 연결된 서비스의 IP / PORT /InstanceId를 가지고 있고 REST기반으로 작동한다.
Client-Sever 방식으로 Eureka Server에 등록된 서비스는 Eureka Client로 불린다.

![img1 daumcdn](https://user-images.githubusercontent.com/24665763/197341914-63cbbe05-325b-433e-8321-f177bc43463d.png)

"Eureka Server와 Eureka Client의 프로세스"

서비스가 Eureka Server에 등록될 때 자신이 살아있다는 상태값을 보낸다.
그리고 Eureka Server는 다른 Eureka Client의 정보들을 제공하고 서비스는 Local Cache에 저장한다.
이후 30초(Default)마다 Eureka Server에 Heartbeats 요청을 보내고 Eureka Server는 90초 안에 Headerbeats가 도착하지 않으면 해당 Eureka Client를 제거한다.


![image](https://user-images.githubusercontent.com/24665763/197343309-c15d1628-bf72-448c-9dd6-3f29036ef9ea.png)

Eureka Client 프로젝트를 생성하고 Eureka Server에서 인스턴스를 확인함.
