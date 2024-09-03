## 메모
- 데이터 일관성
    - write through : 캐시도 db도 저장
    - cache invalidation : 업데이트 마다 캐시 삭제
    - write behind : 캐시는 최신화 db는 배치
- TTL은 incr이나 rename을 사용해도 reset 되지 않음
- 키가 만료되었다고 바로 삭제되는 것이 아님
    - passive : 사용자가 접근할 때 삭제
    - active : 20개의 랜덤한 TTL이 설정된 키를 확인하여 삭제
- max memory
    - noeviction
    - lrueviction : least recently used
    - lfueviction : least frequently used
    - randomevicion
    - volatile-* : ttl에 설정되어 있는 키를 대상으로 동작
- cache stampede
    - concurrent traffic
    - duplicate read
    - duplicate write
    - a.k.a. cascading failure
    - ttl - random() * expiry gap > 0 ? redis.get() : db.get() and redis.set()
    - PER : 만료시간에 가까워 질 수록 random 값에 따라 true로 반환이 될 확률이 높은 알고리즘
- session store

## 개인적인 생각
진짜 아무것도 모르고 운영에서 사용했구나 싶다ㅋㅋㅋㅋ
