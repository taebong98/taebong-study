# taebong-study
이것저것 공부하고 테스트해보기

<details>
<summary>Git Convention</summary>
<div markdown="1">

## Git Convention
### 1. 커밋 유형 지정
- 커밋 유형은 영어 대문자로 작성하기

| 커밋 유형 | 의미   |
|-------|------|
| Feat  | 새로운 기능 추가 |
| Fix  | 버그 수정 |
| Docs  | 문서 수정 |
| Style  | 코드 formatting, 세미콜론 누락, 코드 자체의 변경이 없는 경우 |
| Refactor  | 코드 리팩토링 |
| Test  | 테스트 코드, 리팩토링 테스트 코드 추가 |
| Chore  | 패키지 매니저 수정, 그 외 기타 수정 ex) .gitignore |
| Design  | CSS 등 사용자 UI 디자인 변경 |
| comment  | 필요한 주석 추가 및 변경 |
| Rename  | 파일 또는 폴더 명을 수정하거나 옮기는 작업만인 경우 |
| Remove  | 파일을 삭제하는 작업만 수행한 경우 |
| !BREAKING CHANGE  | 커다란 API 변경의 경우 |
| !HOTFIX  | 급하게 치명적인 버그를 고쳐야 하는 경우 |

### 2. 제목과 본문을 빈행으로 분리
- 커밋 유형 이후 제목과 본문은 한글로 작성하여 내용이 잘 전달될 수 있도록 할 것
- 본문에는 변경한 내용과 이유 설명 (어떻게보다는 무엇 & 왜를 설명)

### 3. 제목 첫 글자는 대문자로, 끝에는 `.` 금지

### 4. 제목은 영문 기준 50자 이내로 할 것

### 5. 자신의 코드가 직관적으로 바로 파악할 수 있다고 생각하지 말자

### 6. 여러가지 항목이 있다면 글머리 기호를 통해 가독성 높이기

</div>
</details>




## H2 Database
### H2 데이터베이스 설치
- https://www.h2database.com/
- 권한 주기: chmod 755 h2.sh
- 데이터베이스 파일 생성
  - jdbc:h2:~/h2db/testDB (최초 1번만)
  - ~/testDB.mv.db 파일 생성 확인
  - 이후 jdbc:h2:tcp://localhost/~/h2db/testDB 로 접속가능

## Log
### 스프링부트에서 Logback 사용하기
##### 1. 앱 개발시 운영 중 발생하는 문제점을 모니터링하거나 추적하는데 용이하다.
##### 2. 데이터를 분석해 통계를 낼 수 있다.
- 스프링 부트에서는 기본적으로 Logback이 설정되어 있다.
- 로그레벨은 기본적으로 [trace > debug > info > warn > error] 순이며 디폴트 설정이 info로 되어있기 때문에 trace와 debug 로그는 기록되지 않는다.

##### 콘솔 로그 수준을 변경하는 가장 간단한 방법은 application.yml이나 application.properties로 설정해주는 것이다
##### 하지만 yml 설정은 스프링부트에서만 가능한 추상화된 방식이기 때문에 이를 사용하려면 문서에서 제공하는 xml로 성절하는 방식을 익혀야 할 필요가 있다.
##### logback-spring.xml 파일을 생성하여 로그를 직접 커스텀 할 수 있다.
- appender: logger를 어디에 출력할지 설정한다. 콘솔, 파일, DB 등 지정할 수 있다.
- FILE 뿐만 아니라 SockerAppender나 LogStash 등도 함께 설정해서 사용할 수 있다.

참고링크: https://loosie.tistory.com/829
