# 내 오답 및 참고노트

<b>DB/데이터베이스 관련</b>
  <b>1.</b>오라클DB에는 Autoincrement기능이 없어서 Sequence를 사용하는 것은 알았으나, 정작 쿼리문에 Sequence를 반영하는 것을 헷갈려 했다....
           Sequence 생성시 초기 값'0'이라는 가정하에 다음값을 불러오는 기능은 SQL에서  <b>"Sequence명.nextval"</b>로 현재 값을 표현할 때는 <b>"Sequence명.currval"</b>로 사용.
  <b>2.</b>MySQL에서는 select문 실행시 출력결과의 갯수를 limit을 통해 제어 가능.
