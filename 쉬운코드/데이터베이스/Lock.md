- 문제점
  - 단순히 값 하나 바꾸는 것보다 더 복잡한 과정
  - 같은 데이터에 또다른 read/write가 있다면 예상치 못한 동작을 할 수 있다.
- Lock
  - ![img_54.png](images/img_54.png)
  - ![img_55.png](images/img_55.png)
  - write-lock (exclusive lock)
    - read/write할 때 사용한다
    - 다른 트랜잭션이 같은 데이터를 read/write 하는 것을 허용하지 않는다.
  - read-lock (shared lock)
    - read할 때 사용한다
    - 다른 트랜잭션이 같은 데이터를 읽는 것은 허용한다.
    - ![img_56.png](images/img_56.png)
    - ![img_59.png](images/img_59.png)
  - lock 호환성
    - ![img_60.png](images/img_60.png)

---
- lock을 사용했음에도 이상한 상황 발생 가능
  - ![img_61.png](images/img_61.png)
  - t1 -> t2
    - ![img_62.png](images/img_62.png)
  - t2 -> t1
    - ![img_63.png](images/img_63.png)
  - 동시
    - ![img_65.png](images/img_65.png)
      - lock을 사용해도 nonserializable임
    - ![img_67.png](images/img_67.png)
      - 이렇게 바꿈
    - 트랜잭션에서 모든 locking operation이 최초의 unlock operation 보다 먼저 수행되도록 하는 것 (2PL protocol)
      - ![img_68.png](images/img_68.png)
      - serializability 보장
        - 문제점
          - 데드락
            - ![img_69.png](images/img_69.png)

---
![img_70.png](images/img_70.png)
![img_71.png](images/img_71.png)
