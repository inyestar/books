## 메모
- 센티널 3대 이상 운영 권고
- 쿼럼 : 마스터가 비정상적이라는 것에 동의하는 센티널의 수
  - 센티널이 3대 이면 쿼럼은 2 (generally)
  - 쿼럼을 만족하면 페일오버 프로세스 시작
  - 하지만 쿼럼 숫자가 절대적이지 않고 실제 센티널 노드 수의 과반수 이상이 동의해야만 odown으로 마킹할 수 있음
- 클라이언트는 센티널에 redis 엔드포인트 질의
- down-after-milliseconds
- sdown -> 쿼럼 -> odown
- epoch : 페일오버가 발생할때마다 증가하는 값 (버전관리)
- split brain

## 개인적인 생각
네트워크 파티션으로 인해 발생하는 스플릿 브레인은 어떻게 해결해야하는거지?
역시 네트워크가 슈퍼 갑이다