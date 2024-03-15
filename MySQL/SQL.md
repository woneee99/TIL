# SQL 문법

## 날짜 데이터 출력
1. 연도 추출 - YEAR(컬럼명)
2. 월 추출 - MONTH(컬럼명)
3. 일 추출 - DAYOFMONTH(칼럼명)
4. 오늘 날짜 관련
    - DATEDIFF(A, B) - A 날짜에서 B 날짜를 빼는 것
    - CURDATE() - 오늘 날짜 추출
5. 날짜 형식 문자열로 추출
    - DATE_FORMAT(날짜(날짜 컬럼), "포맷 형식") <br />
       ex) DATE_FORMAT(NOW(), '%Y-%m-%d')
