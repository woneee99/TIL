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

## 문자열
1. 문자열 합치기
    - CONCAT - CONCAT(문자(데이터), 문자(데이터), ...) AS '칼럼명'
    - || (쌍파이프) - SELECT 데이터1 || 데이터2 || 데이터3 AS '칼럼명'
      
## 숫자 함수
1. ROUND(숫자, 반올림할 자릿수)
2. TRUNCATE(숫자, 버릴 자릿수)

## 조건문
### CASE문
- 아래 두 방법으로 사용 가능
```sql
    CASE STATUS
        WHEN 'SALE' THEN "판매중"
        WHEN 'RESERVED' THEN "예약중"
        WHEN 'DONE' THEN "거래완료"
    END AS STATUS
```
```sql
    CASE 
        WHEN STATUS = 'SALE' THEN "판매중"
        WHEN STATUS = 'RESERVED' THEN "예약중"
        WHEN STATUS = 'DONE' THEN "거래완료"
    END AS STATUS
```
