# 내 오답 및 참고노트<br><br>
<b>DB/데이터베이스 관련</b><br>
<b>1.</b>오라클DB에는 Autoincrement기능이 없어서 Sequence를 사용하는 것은 알았으나, 정작 쿼리문에 Sequence를 반영하는 것을 헷갈려 했다....<br>
Sequence 생성시 초기 값'0'이라는 가정하에 다음값을 불러오는 기능은 SQL에서  <b>"Sequence명.nextval"</b>로 현재 값을 표현할 때는 <b>"Sequence명.currval"</b>로 사용.<br><br>
<b>2.</b>MySQL에서는 select문 실행시 출력결과의 갯수를 limit을 통해 제어 가능.

<b>SPRING 오류 관련</b><br>
<b>오류명 : exception in thread "main" java.lang.unsupportedclassversionerror</b><br>
<b>해결방법</b> jar파일을 통해 배포를 하려고 했는데 상기와 같은 오류가 발생했다....
해결방법은 JDK와 JAVA버전이 안맞아서 나는 오류로 기존 설치된 자바 1.8을 삭제 후 JDK의 버전인 11버전으로 교체하니 다행이 무사히 배포가 성공!


