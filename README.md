# docker-container_1
2
MSA_PROJECT Docker
3
​
4
1. rabbitmq port : 1002
5
2. mysql-user port : 1003
6
​3. mysql-order
4. mysql-product
5. 


1. 도커 네트워크 생성
docker network create --gateway 172.18.0.1 --subnet 172.18.0.0/16 ecommerce-network

2. 도커 실행
all 디렉토리에서 docker compose up

프론트 접속 포트 1221

프론트(nginx) -> apigateway(해당 서비스 서버 uri 매칭) -> 해당 서버 -> 리턴


카프카 사용 예)
유저 -> 상품과 주문간의 이벤트 형성 (상호간의 pub, sub)

FeignClient 사용 예)
외부 통신 -> feignClient(restTemplate과 유사하다) 유레카에 등록된 서비스간의 통신에 사용됨 (현재는 상품 서버와 주문 서비스간에 사용됨)

RestDocs 전체적으로 주요 api 사용시 사용 예)
유저, 주문, 상품

SpringConfigSever 사용 예)
전체적인 프로퍼티 깃허브에 생성 -> configServer에서 로드 -> 유저, 주문, 상품 서버 로드시 configServer에서 정보 로드
https://github.com/JEONSEUNGREE/config-server_1

7
​
8
<!-- 
9
카프카와 주키퍼 간략 설명
10
프로듀서 : 카프카와 통신하면서 메시지를 보내는 역할
11
컨슈머 : 카프카와 통신하면서 메시지를 가져오는 역할
12
주키퍼 : 컨슈머와 통신, 카프카의 메타데이터 정보를 저장, 카프카의 상태관리 등 목적으로 이용
13
주키퍼는 클러스터가 과반수이상 다운되면 서비스 중지됨
14
ex) 총 3대 -> 2대 다운시 서비스 중지
15
    총 3대 -> 1대 다운시 서비스 유지
16
 -->
