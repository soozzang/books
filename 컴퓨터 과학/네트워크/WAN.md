## Wide Area Network (WAN)
- ![img_13.png](image/image2/img_13.png)
  - 위와 같이, 라우터는 LAN들을 연결시켜주기도 하지만,
- ![img_14.png](image/image2/img_14.png)
  - 위 처럼 라우터끼리도 연결을 한다.
  - 수 많은 라우터들이 연결되어 있는게 곧 인터넷이다.
- 라우터와 라우터 간에는 MAC 주소를 사용하지 않는다.
  - ![img_15.png](image/image2/img_15.png)
- 다신 IP 주소를 사용한다.
  - ![img_16.png](image/image2/img_16.png)
  - 라우터들, LAN에 연결되어 있는 로컬 컴퓨터들 또한 IP주소를 갖는다.

## IP 주소
- IP 주소는 전략적으로 배치된다.
  - 사람이 직접 할당하기도 하고, 자동적으로 할당하기도 한다.

## 프레임와 패킷
- ![img_17.png](image/image2/img_17.png)
  - 위 처럼 LAN에선 프레임을 주고 받는다.
- ![img_18.png](image/image2/img_18.png)
  - 그래서 패킷도 같이 보낸다.
    - ![img_19.png](image/image2/img_19.png)
  - ![img_20.png](image/image2/img_20.png)

## 라우팅
- LAN 안에선 이더넷 프레임을 통해 정보를 보내고,
- 라우팅하는 과정에선 패킷만 따로 보낸다.
- 그리고 라우터들을 거쳐서 LAN으로 도착할 떈 프레임으로 다시 감싸서 보낸다(보내고 싶은 컴퓨터 에게).
- ![img_21.png](image/image2/img_21.png)

---
![img_22.png](image/image2/img_22.png)
- 위의 빨간 선과 같은 경로로 데이터를 보내고 싶다면, 어떻게 전달될까?

<br>

![img_24.png](image/image2/img_24.png)
- LAN에서 정보를 보내기 위해선 이더넷 프레임을 사용을 해줘야만 했다.
- 이 프레임을 사용하기 위해선, 보내는 쪽의 MAC주소와 보내는 곳의 MAC주소가 필요하다.
- 하지만 라우터의 MAC 주소는 알 수가 없다. (공유기에 붙어있는 MAC주소가 라우터의 MAC 주소이긴 하다..)
- 하지만 컴퓨터는 직접 공유기를 보고 MAC주소를 알아낼 수 없다. (연결만 되기 때문에)
- 다행히 IP 주소는 알고 있다.
  - ip주소는 전략적으로 할당되기 때문,(MAC 주소는 랜덤인 반면) 그말은 즉! 네트워크 설계가 가능하다.
- 하지만 여전히 문제, IP주소는 알지만 MAC 주소는 모르는 상황
  - 우리가 LAN의 컴퓨터에서 라우터로 정보를 보내려면 프레임을 이용해야 한다.
  - 하지만 아직, 라우터의 MAC 주소를 모르기 때문에 보낼 수가 없는 상황이다.
  - 다행인것은, ip 주소를 통해 MAC 주소를 알 수 있다 !
    - 이것은 `ARP` (Address Resolution Protocol) 라고 부른다.
- ip 주소 vs MAC 주소
  - MAC 주소는 하드웨어 정보, IP 주소는 하드웨어 위치 정보

## ARP
- 라우터의 MAC 주소를 알기 위해, `ARP 패킷` 이라는 것을 LAN의 모든 디바이스들에 보내면서 라우터의 MAC 주소를 알아낼 수 있다.
- ![img_25.png](image/image2/img_25.png)
- ![img_27.png](image/image2/img_27.png)
- 그렇다면 ARP의 과정을 살펴보자
  - ![img_28.png](image/image2/img_28.png)
  - ![img_30.png](image/image2/img_30.png)
  - ![img_29.png](image/image2/img_29.png)
  - ![img_31.png](image/image2/img_31.png)
  - ![img_32.png](image/image2/img_32.png)
  - ![img_33.png](image/image2/img_33.png)


## 이더넷 프레임과 ARP 패킷
- 이더넷 프레임
  - ![img_34.png](image/image2/img_34.png)
  - ![img_36.png](image/image2/img_36.png)
  - ![img_37.png](image/image2/img_37.png)
  - ![img_38.png](image/image2/img_38.png)
  - ![img_39.png](image/image2/img_39.png)

## ARP 정리
![img_43.png](image/image2/img_43.png)

## 이더넷 프레임과 IP 패킷
- 이제 ARP를 통해서 라우터의 MAC 주소를 알았다.
- ![img_44.png](image/image2/img_44.png)

<br>

- 이제 IP 패킷을 프레임에 넣자
  - ![img_45.png](image/image2/img_45.png)
  - ![img_46.png](image/image2/img_46.png)
  - ![img_47.png](image/image2/img_47.png)
  - ![img_48.png](image/image2/img_48.png)
  - ![img_49.png](image/image2/img_49.png)

## 라우터와 라우터간 소통
![img_50.png](image/image2/img_50.png)
![img_51.png](image/image2/img_51.png)
![img_52.png](image/image2/img_52.png)
![img_53.png](image/image2/img_53.png)
![img_54.png](image/image2/img_54.png)
![img_55.png](image/image2/img_55.png)
![img_56.png](image/image2/img_56.png)
![img_57.png](image/image2/img_57.png)
![img_59.png](image/image2/img_59.png)
![img_60.png](image/image2/img_60.png)


<br>

- ppp 프레임에 감싸서 라우터끼리 소통
![img_58.png](image/image2/img_58.png)

## WAN to LAN
![img_61.png](image/image2/img_61.png)
![img_62.png](image/image2/img_62.png)
![img_63.png](image/image2/img_63.png)
![img_64.png](image/image2/img_64.png)