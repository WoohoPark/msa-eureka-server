<h1>Eureka</h1>
MSA와 같은 분산 환경은 서비스 간의 원격 호출로 구성이 된다.<br>
원격 서비스 호출은 IP 주소와 포트를 이용하는 방식이 되는다.<br>
클라우드 환경이 되면서 서비스가 오토 스케일링등에 의해서 동적으로 생성되거나 컨테이너 기반의 배포로 인해서, 서비스의 IP가 동적으로 변경되는 일이 잦아졌다.<br>
그래서 서비스 클라이언트가 서비스를 호출할때 서비스의 위치 (즉 IP주소와 포트)를 알아낼 수 있는 기능이 필요한데, <br>
이것을 바로 서비스 디스커버리 (Service discovery)라고 한다. 여기서 Service Discovery 역할을 하는 것이 Eureka라고 말할 수 있다.<br>
Eureka는 AWS와 같은 Cloud 시스템에서 서비스의 로드 밸런싱과 실패처리 등을 유연하게 가져가 위해 각 서비스들의 IP,Port,InstanceId를 가지고 있는 REST 기반의 미들웨어 서버입니다.<br>

<h2>Eureka Server와 Eureka Client의 프로세스</h2>

1. Eureka는 Client-Server의 방식으로 Eureka Server는 모든 Client 서버들이 본인의 IP와 Port, InstanceId를 Eureka-Server로 전달합니다. 그리고 Eureka에 있는 정보를 Fetch하여 Eureka-Client간 통신에 사용합니다.<br>

2. 서비스가 Eureka Server에 등록될 때 자신이 살아있다는 상태값을 보낸다.<br>
이후 30초(Default)마다 Eureka Server에 Heartbeats 요청을 보내고 Eureka Server는 90초 안에 Headerbeats가 도착하지 않으면 해당 Eureka Client를 제거한다.<br>

![img1 daumcdn](https://user-images.githubusercontent.com/24665763/197341914-63cbbe05-325b-433e-8321-f177bc43463d.png)
* eureka에 각자의 ip / port를 등록하여 http 통신에 사용한다.

![image](https://user-images.githubusercontent.com/24665763/197344430-2fc5a040-f7b1-4955-bce5-d1d195386f38.png)
* HTTP통신으로 Eureka Client 등록,조회,삭제 등 다양한 기능을 사용할 수 있다.

![image](https://user-images.githubusercontent.com/24665763/197343309-c15d1628-bf72-448c-9dd6-3f29036ef9ea.png)
* Eureka Sever와 Client를 통신하고 Instance가 생성됨.
 
 

* 출처
https://tmdrl5779.tistory.com/181?category=875847

