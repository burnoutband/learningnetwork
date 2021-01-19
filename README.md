# Youtube로 배우는 Network

## 1 Hub, Switch & Router

### 동영상

- https://youtu.be/1z0ULvg_pW8

### 요약

- Hub 

	- 데이터가 하나 유입되면 나머지 포트에 복사해서 Brodcast 함

		- 네트워크에 부하발생

	- 같은 네트워크에서 사용

		- same subnet

	- OSI 7 계층 layer 1 device

		- https://youtu.be/MeSRaKrOCYk?t=67

		- Bit 데이터 취급
		- 리피터도 해당됨

- Switch

	- mac address 사용하는 장비

		- bridge 장비도 mac address 사용

			- 보통 두 허브 사이에 두고 사용한다.

	- Mac address 를 테이블로 보관하여 그걸 보고 1대1 통신함
	- 같은 네트워크에서 사용

		- same subnet

	- OSI 7 계층 Layer 2 device

		- https://youtu.be/MeSRaKrOCYk?t=155

		- 이더넷 Frames 데이터를 취급

	- L3, L4, L7 스위치

		- http://wiki.hash.kr/index.php?title=%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC_%EC%8A%A4%EC%9C%84%EC%B9%98&mobileaction=toggle_view_desktop

- Router

	- 패킷내의 IP 검사하여 패킷이 자체 네트워크 용인지 다른 네트워크 용인지 확인함

		- Routing table에 해당 IP 정보 있으면 수신
		- Routing table에 해당 IP 정보 없으면 다르네트워크로 보냄

	- 본질적으로 네트워크의 게이트웨이임
	- IP 사용하는 장비
	- OSI 7 계층 Layer 3 device

		- https://youtu.be/MeSRaKrOCYk?t=196

		- Data package 를 취급

- 결론

	- Hub & Switch 는 네트워크를 구성할 때 사용
	- Router 는 네트워크와 네트워크를 연결할 때 사용

- Hub, Switch & Router 배치

	- https://www.geeksforgeeks.org/difference-between-router-and-switch/

## 2 Firewall

### 동영상

- https://youtu.be/vrh0epPAC5w?t=1444

### 요약

- ACL (Access Control List)

	- ACL 가지고 제어함

		- https://youtu.be/vrh0epPAC5w

		- implicit deny 정책

- Firewall type

	- Host based

		- software firewall
		- 컴퓨터한대에 설치해서 그 컴퓨터만 보호

	- Network based

		- 네트워크 전체에 적용

	- stateful

		- connections, data streams 모두 모니터링함

	- stateless

		- acl 사용하는 firewall

	- firewall

		- firewall_image.jpg

## 3 IDS / IPS

### 동영상

- https://youtu.be/_gHMkEKGwBM

- https://www.youtube.com/watch?v=rvKQtRklwQ4

### 요약

- IDS (Intrusion Detection System)

	- 작동위치

		- 본인 서비스 네트워크 안에서 작동 (방화벽 뒤에 존재함)

	- 역할

		- 위험을 감지하고 알림을 전송함
		- Switch 에서 거쳐가는 데이터를 모두 감시

	- 타입

		- HIDS : Host-based IDS on Computer
		- NIDS : Network-based IDS on network

- IPS (Intrusion Protection System)

	- 역할

		- 위험을 감지하고 알림을 전송함
		- 보호방법

			- signature match 를 통해서 차단

				- signature DB의 내용과 비교작업을 수행함

			- Anomaly Detection 통해서 차단

				- 정상트래픽 기준설정하고 그것과 다르면 차단

## 4 DMZ

### 동영상

- https://youtu.be/dqlzQXo1wqo?list=PL7zRJGi6nMRzHkyXpGZJg3KfRSCrF15Jg

## Datacenter network architecture

## 패킷의 여행 (A to Z)

### https://youtu.be/EOYe71RWMvk

## 정신건강에 도움되는 자료

### CISCO LAN design

- https://www.cisco.com/c/en/us/solutions/design-zone.html#~featured

### Cable

- https://youtu.be/vrh0epPAC5w

### cisco icon
- https://www.cisp.or.kr/wp-content/uploads/2020/01/Cisco-Network-Topology-Icons.zip
- https://www.cisco.com/c/dam/en_us/about/ac50/ac47/icon-library-production-oct2016.zip

### Internet ---> Router ---> Firewall ---> IDS/IPS ---> Switch ---> 서버

## 최초 작성일

### 2021-01-19

