# <u>트랜스포트 계층이란(Transport-layer)</u>

Transport layer는 서로 다른 호스트에 있는 application processes들 간의 논리적 커뮤니케이션을 제공하는 layer이다.

---
***Multiplexing과 Demultiplexing***

* Multiplexing
    * Application layer 에서 패킷이 소켓에 의해 Transport layer 로 전달 될 때, 여러 소켓의 패킷을 수집하여 하나의 세그먼트에 캡슐화하여 Network layer로 전달하는 과정
* Demultiplexing
    * Transport layer 에서 세그먼트가 Application layer 로 전달 될 때, 올바른 소켓으로 전달 하는 과정

***TCP 와 UDP***

* UDP
    * Destination Port number만 고려
    * non - reliable
    * DNS, streaming 영상 등에 사용
* TCP
    * Source Ip, dest Ip, source port, dest port
    * reliable
    * in order delivery
    * flow control(흐름제어) -> 상대방 상태
    * congestion control(혼잡제어) -> 네트워크 상태

---
***TCP***

* TCP segment structure
    * source port
    * dest port
    * sequence number
    * ACK
    * checksum
    * receive window -> 상대 빈 공간 확인용

* flow control
    * 송신측과 수신측의 데이터처리 속도 차이를 해결하기 위한 기법이다.
    * 수신측이 송신측보다 속도가 빠른 것은 아무 문제가 되지 않는다.
    * 송신측이 수신측보다 속도가 빠르면 문제가 발생한다.
    * nagle 알고리즘
        * 상대방이 받을 수 있는 사이즈(window size)와 보낼 데이터가 MSS(최대 세그먼트 크기) 보다 크다면 바로 전송한다.
        * 위 조건에 해당하지 않는다면 전송한 모든 패킷이 승인 될때까지(ACK을 받을 때까지) 버퍼에 모은다(Nagle On)
        * 모든 패킷이 승인 되었다면 패킷을 전송한다.
* congestion control
    * 라우터에서 버퍼가 오버플로우되어 패킷 손실의 발생
    * 라우터 버퍼에서 긴 큐잉 지연(Queueing delay) 발생
    * AIMD (Additvie Increase Multiplicative Decrease)
        * 혼잡 윈도우 크기(Congestion Window Size, cwnd) : 수신측의 윈도우 크기(rwnd)에 영향을 받으며, 송신측에 있는 윈도우 크기이다.
        * 가법적 증가(Additive Increase)
            * 손실이 발견될 때까지 매 RTT(왕복시간)마다 1MSS씩 cwnd를 증가시킨다.
        * 승법적 감소(Multiplicative Decrease)
            * 손실이 발생한 후에 cwnd를 절반으로 감소시킨다.


