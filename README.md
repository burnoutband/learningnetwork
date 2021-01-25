# 스터디 정책
- 주제선정
	- 데이터센터 네트워크 이해
	- 서버-클라이언트간 데이터 전송 이해
- 운영방식
	- 매주 / 1가지 주제 / 20분 내외
	- 자발적 참여 (참여자 없으면 운영자가 ...)

# Table of Contents
- [Youtube로 배우는 Network](#youtube------network)
  * [1. Datacenter network architecture](#1-datacenter-network-architecture)
    + [1.1 Hub, Switch & Router](#11-hub--switch---router)
    + [1.2 Firewall](#12-firewall)
    + [1.3 IDS / IPS](#13-ids---ips)
    + [1.4 DMZ](#14-dmz)
  * [2. 패킷의 여행 (A to Z)](#2---------a-to-z-)
  * [※ 정신건강에 도움되는 자료](#---------------)
    + [CISCO Datacenter Design playbook](#cisco-datacenter-design-playbook)
    + [cisco icon](#cisco-icon)
    + [Cable](#cable)
    + [Internet ---> Router ---> Firewall ---> IDS/IPS ---> Switch ---> 서버](#internet------router------firewall------ids-ips------switch--------)
  * [최초 작성일](#------)
    + [2021-01-19](#2021-01-19)

<small><i><a href='http://ecotrust-canada.github.io/markdown-toc/'>Table of contents generated with markdown-toc</a></i></small>


# Youtube로 배우는 Network
## 스터디 정책
### 주제선정
- 데이터센터 네트워크 구조
- 서버 - 클라이언트 간 데이터 전송 이해
### 운영
- 매주 / 1가지 주제 / 20분 내외
- 자발적 참여
	- 참여자 없으면 운영자가 발표
## 1. Datacenter network architecture
### 1.1 Hub, Switch & Router
- 동영상
	- https://youtu.be/1z0ULvg_pW8
- 요약
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
		- Destination MAC 주소만 확인하고 포워딩시킴
		- L3, L4, L7 스위치
			- http://wiki.hash.kr/index.php?title=%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC_%EC%8A%A4%EC%9C%84%EC%B9%98&mobileaction=toggle_view_desktop
			- L3 스위치
				- https://youtu.be/KA4-z6mBQxI
				- https://cardinals.tistory.com/78?category=612430
	- Router
		- 패킷내의 IP 검사하여 패킷이 자체 네트워크 용인지 다른 네트워크 용인지 확인함
			- Routing table에 해당 IP 정보 있으면 수신
			- Routing table에 해당 IP 정보 없으면 다르네트워크로 보냄
		- 본질적으로 네트워크의 게이트웨이임
		- IP 사용하는 장비
		- OSI 7 계층 Layer 3 device
			- https://youtu.be/MeSRaKrOCYk?t=196
			- Data package 를 취급
		- L2 MAC
	- 결론
		- Hub & Switch 는 네트워크를 구성할 때 사용
		- Router 는 네트워크와 네트워크를 연결할 때 사용
	- Hub, Switch & Router 배치
		- https://www.geeksforgeeks.org/difference-between-router-and-switch/
### 1.2 Firewall
- 동영상
	- https://youtu.be/vrh0epPAC5w?t=1444
- 요약
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
### 1.3 IDS / IPS
- 동영상
	- https://youtu.be/_gHMkEKGwBM
	- https://www.youtube.com/watch?v=rvKQtRklwQ4
- 요약
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
### 1.4 DMZ
- 동영상
	- https://youtu.be/dqlzQXo1wqo?list=PL7zRJGi6nMRzHkyXpGZJg3KfRSCrF15Jg
### 1.5 VLAN
- 동영상
	- https://www.youtube.com/watch?v=ILv_-eQX7XU
- Port Group 이라고도 함
- vlan 구현 방식은 여러가지
	- 벤더마다 구현 방식이 다름
		- 스위치
	- 설정예제
		- 1 switch 접속
		- 2 vlan 생성 및 이름생성
		- 3 switch 포트들을 특정 vlan 에 매핑
- 기본적으로 물리적 스위치의 남는 포트활용을 목적을함
### 1.6 Overay Network
- VXLAN
### Current Datacenter Network
- https://www.youtube.com/watch?v=6-66D9J5PkY
	- 구성
		- 전통방식
			- 라우터
			- Core 스위치
				- 백본스위치
			- 분배 스위치
			- ToR 스위치
				- access switch
				- 랙 맨위에 설치
			- 특징
				- 분산형 정책관리 / 운영
				- 폐쇄적 네트워크 운영체제
				- 계층형 (티어링) 네트워크 아키텍처
				- 분업형 인프라 관리 조직
				- 서비스 증설시 증설대상
					- 서버랙
					- 네트워크 장비
					- 스토리지 장비
		- Leaf / Spine 방식
	- 변화이유(전통방식 --> Leaf / Spine 방식)
		- 하이브리드 클라우드
		- 인프라측면의 민첩성 강조
		- 자동화 추세
			- 스크립트 수준을 넘어가고 있음
		- 정책 기반
			- 사용자 의도파악에 방점
		- https://www.slideshare.net/CiscoKorea/2-60481681
		- https://youngmind.tistory.com/entry/%E2%80%9C%ED%81%B4%EB%9D%BC%EC%9A%B0%EB%93%9C%EC%BB%B4%ED%93%A8%ED%8C%85%EC%9D%84-%EC%9C%84%ED%95%9C-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EC%84%A4%EA%B3%84%EB%A5%BC-%EB%A7%90%ED%95%98%EB%8B%A4%E2%80%9D?category=394662
			- EAST - WEAS 흐름이 더 많음
## 2. 패킷의 여행 (A to Z)
### IP Packet 및 Ethernet Frame 전송방식
- 동영상
	- https://www.youtube.com/watch?v=zhlMLRNY5-4
- 전송 데이터
	- IP Packet & Frame
		- https://m.blog.naver.com/PostView.nhn?blogId=sujunghan726&logNo=220315439853&proxyReferer=https:%2F%2Fwww.google.com%2F
- 전송 장치
	- Switch (L2)
		- Destination MAC Address 만 확인하고 해당 포트로 포워딩함
	- Router
		- 1 Destination MAC Address를 보고 나한테 온 것인지 확인함
		- 2 IP 정보를 확인하기 위해 IP packet 을 확인함
		- 3 목적지 컴퓨터에 보내기 위해 다시 헤더 (Destination MAC Address) 를 작성하여  새로운 Frame 을 작성함
### Ethernet Frame
- 동영상
	- https://youtu.be/JsYqqDqmQaE
- 구조
	- 그림
		- https://youtu.be/JsYqqDqmQaE?t=125
	- Preamble
		- frame 시작점 확인역할 (11로 끝나는 값으로 확인)
	- Destination MAC
		- Default GW / Router MAC 정보가 들어있음
	- Source MAC
		- 데이터 보내는 컴퓨터 MAC
	- Type
		- Data 속성 설명
	- Data
	- FCS (frame check sequence)
		- Frame 오류 확인용도
		- Ethernet 네트워크를 사용하는 컴퓨터는 FCS 코드를 frame 에 붙여서 사용
			- fcs code는 CRC 알고리즘으로 생성
### 참고
- https://youtu.be/EOYe71RWMvk
## ※ 정신건강에 도움되는 자료
### Cable
- https://youtu.be/vrh0epPAC5w
### Internet ---> Router ---> Firewall ---> IDS/IPS ---> Switch ---> 서버
### 네트워크 전반
- https://www.youtube.com/c/NetworkingClass/playlists?view=50&sort=dd&shelf_id=2
## 최초 작성일
### 2021-01-19
## CISCO section
### CISCO Datacenter Design playbook
- https://www.cisco.com/c/dam/en/us/solutions/collateral/enterprise-networks/enterprise-network-security/data-center-design-playbook.pdf
### Cisco icon
- https://www.cisp.or.kr/wp-content/uploads/2020/01/Cisco-Network-Topology-Icons.zip
- https://www.cisco.com/c/dam/en_us/about/ac50/ac47/icon-library-production-oct2016.zip
### CCNA
- 강좌
	- Free CCNA (networkchuck)
		- https://youtu.be/S7MNX_UD7vY
	- 계영수
		- https://youtu.be/JfuPLQ6DIcg
- 내용
	- Spine and Leaf architecture
		- https://www.cisco.com/c/en/us/products/collateral/switches/nexus-7000-series-switches/white-paper-c11-737022.html#Spineandleafarchitecture
- 교재
	- Volume 1
		- https://drive.google.com/file/d/1EPGHrEn5XjflHNOfl1jqQxY3LAgcNFzG/view
	- Volume 2
		- https://drive.google.com/file/d/1wRzBgEf-igqH3wf8gEDe7XjQ5LqClTBV/view
	- https://learningnetworkstore.cisco.com/
### 장비
- Cisco Nexus 7000
	- https://www.cisco.com/c/dam/global/ko_kr/products/switches/nexus-7000-series-switches/Cisco_Nexus_7000_F2-Series_48-Port_1_and_10_Gigabit_Ethernet_Module_data_sheet.pdf
	- L2 & L3 스위치
*XMind - Trial Version*
