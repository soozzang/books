- unrecoverable schedule

  ![img_40.png](images/img_40.png)
  - t2는 롤백했지만, t1은 커밋함
- recoverable schedule(최종 목표)
  ![img_41.png](images/img_41.png)
- cascading rollback

  ![img_42.png](images/img_42.png)

  - 하지만 여러 트랜잭션의 롤백이 연쇄적으로 일어나면 cascading rollback 방식으론 처리하는 비용이 많이 든다.
    - 해결 -> 데이터를 write한 transaction이 commit/rollback 한 뒤에 데이터를 읽는 schedule만 허용하자!
      ![img_43.png](images/img_43.png)
      ![img_45.png](images/img_45.png)
      - 하지만 문제 존재
      
        ![img_46.png](images/img_46.png)
        ![img_48.png](images/img_48.png)
      - 보강 필요
      
        ![img_49.png](images/img_49.png)
        ![img_50.png](images/img_50.png)
      - strict schedule
        - 롤백을 할 때 recovery가 쉽다.
        - 트랜잭션 이전 상태로 돌려놓기만 하면 된다.
---

![img_51.png](images/img_51.png)

![img_52.png](images/img_52.png)