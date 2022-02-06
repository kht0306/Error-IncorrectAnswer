# 내 오답 및 참고노트<br><br>
<b>DB/데이터베이스 관련</b><br>
<b>1.</b>오라클DB에는 Autoincrement기능이 없어서 Sequence를 사용하는 것은 알았으나, 정작 쿼리문에 Sequence를 반영하는 것을 헷갈려 했다....<br>
Sequence 생성시 초기 값'0'이라는 가정하에 다음값을 불러오는 기능은 SQL에서  <b>"Sequence명.nextval"</b>로 현재 값을 표현할 때는 <b>"Sequence명.currval"</b>로 사용.<br><br>
<b>2.</b>MySQL에서는 select문 실행시 출력결과의 갯수를 limit을 통해 제어 가능.

<b>SPRING 오류 관련</b><br>
<b>오류명 : exception in thread "main" java.lang.unsupportedclassversionerror</b><br>
<b>해결방법</b> jar파일을 통해 배포를 하려고 했는데 상기와 같은 오류가 발생했다....
해결방법은 JDK와 JAVA버전이 안맞아서 나는 오류로 기존 설치된 자바 1.8을 삭제 후 JDK의 버전인 11버전으로 교체하니 다행이 무사히 배포 성공!


<b>SPRING BOOT MyBatis오류 관련</b><br>
<b>오류명 : org.springframework.beans.factory.UnsatisfiedDependencyException</b><br>
<b>해결방법</b> mapper xml파일에서 resultType타입을 제대로 맞추지 않아서 오류 난것으로 실제 매게변수로 받은 타입으로 제대로 수정하니 완성! 


<b>오류 일찍 해결해 버려서 오류명은....기억안남</b><br>
<b>해결방법</b> mapper의 쿼리문에 매개변수를 바인딩 처리할 때 넣는 매겨변수가 null값일때 sql null관련 오류 발생할 때 #{파라미터명, jdbcType=VARCHAR}처럼
jdbcType="파라미터 타입"을 입력하면 해결 가능

<b>SPRING BOOT MyBatis 동적쿼리 관련 오류</b><br>
<b>오류명 : SQL EXCEPTION : nested exception is org.apache.ibatis.type.TypeException: Could not set parameters for mapping: ParameterMapping{property='clntName', mode=IN, javaType=class java.lang.Object, jdbcType=VARCHAR, numericScale=null, resultMapId='null', jdbcTypeName='null', expression='null'}. Cause: org.apache.ibatis.type.TypeException: Error setting null for parameter #5 with JdbcType VARCHAR . Try setting a different JdbcType for this parameter or a different jdbcTypeForNull configuration property. Cause: java.sql.SQLException: 부적합한 열 인덱스 </b><br>
<b>원인</b> 쿼리문에 특수문자가 들어 갈 수도 있겠다고 생각에 안전하게 CDATA[쿼리문]>을 통해 SQL를 작성했는데 저 안에 SQL문을 쓰면 동적쿼리를 위한 <if>문까지 쿼리문으로 인식하여
동적으로 처리가 불가능해졌음.....ㅎㅎ CDATA[쿼리문] 밖으로 if절을 꺼내니 이상없이 정상 기능이 됨


<b>JAVA 오류 관련.... 기본적인 부분</b><br>
<b>오류명 : NULL POINT EXCEPTION
<b>문제원인</b> : 기본적인 이유였는데 자꾸 Map, List 등의 객체 선언시, 변수로 자꾸 착각하고 Map<String, String> map = null; 처리를 가끔한다.... 객체라는 걸 잊지 말고 new Map<>(); 처리를 반드시 하자.....!
