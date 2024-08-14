## 메모
- key-value
    - string : 512mb, binary safe
    - list : array
    - hash : hgetall
    - set
    - sorted set : sorted by score and dictionary order (ascii bytes) when scores are same
    - bitmap 
    - hyperloglog
    - geospatial
    - stream
- XX : 이미 존재할 때만 추가
- NX : 없을때만 추가
- 0 -1는 전체를 의미
- 자료구조마다 다른 get, set 커맨드
- binary safe : null을 포함한 모든 바이트 시퀀스를 처리 할 수 있으며 raw를 그대로 다루기 때문에 오디오, 이미지 가능
- stream, set, sorted set, hash는 키를 명시적으로 지정하지 않아도 알아서 생성 됨
- stream을 제외하고 key의 value가 모두 삭제되면 키는 삭제 됨
- 그냥 지우기보단 key와 value를 끊는 unlink로 먼저 관계부터 없애는게 성능상 나음

## 개인적인 생각
- string은 multi lock
- list는 큐나 스택
- hash는 액세스 토큰이나 세션 저장
- set은 교집합 차집합이 가능하니까 추천에서 사용할 수 있을라나?
- sorted set은 모르겠다
