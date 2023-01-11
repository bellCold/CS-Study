# <u>링크 계층이란(Link-layer)</u>

링크 제어 프로토콜(Link Control Protocols)을 사용하여 프레임을 전송하며, 에러 검출, 흐름 제어, 액세스 제어 등의 기능을 제공합니다.

---
***Multiple Access Protocols(MAC)***

동시에 같은 링크 채널에 데이터를 전송하면 충돌이 일어난다. 이때 충돌이 일어나면 제대로 된 데이터가 전송되지 않기 때문에, 여러 노드가 한번에 하나의 링크에 데이터를 보내지 않도록 제어해줘야 한다. 즉,
Multiple Access가 일어나지 않도록 제어Multiple Access Control(MAC)을 해줘야 한다.

1) Channel Partition
    * TDMA(Time Division Multiple Access)
        * 하나의 채널을 쪼갠 후 라운드로빈 방식으로 메시지를 전송하는 방식.
        * 효율이 좋지 않다.
    * FDMA(Frequency Division Multiple Access)
        * FDMA는 하나의 주파수를 쪼개서 통신하는 방식이다. 즉 하나의 도로를 8차선 도로로 바꿔서 사용한다고 이해하면 된다.

2) Radom Access Protocols
    * CSMA (carrier sense multiple access)
        * listen before transmit 방식으로 동작
        * 다른 node에서 packet bit를 전송하고 있는지 확인 후에 전송.
        * 만약 channel이 busy면 일정시간 딜레이 한후 전송

    * CSMA/CD(Collision detection)
        * CSMA와 동일한 방식으로 collision이 발생하면 짧은 시간안에packet bit 전송을 양쪽에서 멈춘다.
        * 짧은 시간안에 collision을 감지함으로써 channel의 시간 낭비를 줄일 수 있다.
        * CSMA/CD : 충돌이 발생하면 중단 요청 신호를 보낸다.

3) Taking Turns
    * Polling (사회자 같은 역할)
        * 마스터 노드와 슬레이브 노드가 존재한다. 마스터는 전송을 시작해도 되는 슬레이브를 순서대로 지정한다. 슬레이브는 지정받은 번호표에 맞춰 전송을 시작한다.
    * Token Passing
        * 하나의 네트워크에 참여한 모든 노드들은 Token을 공유한다. 그리고 해당 Token을 가진 자만이 데이터를 전송할 수 있다. 그리고 자신의 전송이 끝나면 옆 친구에게 Token을 전달하면서
          순서대로 데이터를 전송한다.

---     
***Ethernet***

컴퓨터 네트워크 기술의 하나로, 전세계의 사무실이나 가정에서 일반적으로 사용되는 LAN에서 가장 많이 활용되는 기술 규격이다.

* 이더넷은 CSMA/CD (carrier sense multiple access with collision detection 반송파 감지 다중 접속 및 충돌 탐지) 기술을 사용한다. 이 기술은 이더넷에 연결된 여러
  컴퓨터들이 하나의 전송 매체를 공유할 수 있도록 한다. 어떤 컴퓨터가 이더넷 네트워크를 사용하는 경우 다음과 같은 과정을 거친다.

1. 네트워크를 사용하려는 컴퓨터는 먼저 현재 네트워크 위에 흐르고 있는 데이터가 있는지를 감지한다.
2. 만약 현재 다른 데이터가 전송 중이면 사용할 수 있을 때까지 기다리고 아니면 전송을 시작한다.
3. 여러 군데에서 동시에 전송을 시작해 충돌이 발생하면 최소 패킷 시간 동안 전송을 계속해, 다른 컴퓨터가 충돌을 탐지할 수 있도록 한다.
4. 그 뒤, 임의 시간 동안 기다린 뒤에 다시 신호(반송파)를 감지하고, 네트워크 사용자가 없으면 전송을 다시 시작한다.
5. 전송을 마치면, 상위 계층에 전송이 끝났음을 알리고 끝마친다.
6. 여러 번 다시 시도했음에도 전송에 실패하면 이를 상위 계층에 알리고 끝마친다. 오늘날에는 대부분 이더넷 스위치를 사용하여 스위치 방식의 네트워크(switched network)를 구성하는데, 이 경우 충돌이
   일어나지 않는다.

* 이더넷 스위치 : 이더넷 프레임을 전달하는 링크계층 스위 칭 장비이다. 이더넷 스위치 특징은 이더넷 MAC(Mac Access Control) 주소를 기반으로 이더넷 프레임을 필요한 포트에게만 선택적으로 전달해주는
  장비이다.

---

***ARP( Address Resolution Protocol)***

IP 주소를 MAC 주소와 매칭 시키기 위한 프로토콜입니다.
 