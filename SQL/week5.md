# 📘 SQL_BASIC 5주차 정규 과제

SQL_BASIC 정규 과제는 매주 정해진 분량의 `초보자를 위한 BigQuery(SQL) 입문` 강의를 듣고, 핵심 개념을 정리한 뒤 간단한 SQL 문제를 직접 풀어보는 방식으로 진행합니다.

이번 주는 날짜/시간 데이터와 조건문을 학습합니다. 특히 `CASE WHEN`은 SQL 문제 풀이와 데이터 분석에서 자주 사용되므로, 직접 분류 기준을 만들고 결과를 확인하는 연습을 해주세요.

완성된 과제는 Github에 업로드하고, 링크를 스프레드시트 'SQL' 시트에 입력해 제출해주세요.

**👀 수행 인증란은 필수입니다.**

---

## 📚 SQL_BASIC_5th_TIL

### 섹션 5. 데이터 탐색 - 변환

### 4-4. 날짜 및 시간 데이터 이해하기

### 4-6. 조건문(CASE WHEN, IF)

---

## ✨ 선택 강의

- 4-5. 시간 데이터 연습문제: 날짜/시간 함수를 더 연습하고 싶을 때 선택 수강
- 4-7. 조건문 연습문제: CASE WHEN과 IF를 더 연습하고 싶을 때 선택 수강

---

## 🏁 전체 강의 수강 계획

| 주차 | 필수 강의 범위 | 선택 강의 | 완료 여부 |
| --- | --- | --- | --- |
| 1주차 | 1-1 ~ 2-1 | 1 | ✅ |
| 2주차 | 2-2 ~ 2-3 | 2-4 | ✅ |
| 3주차 | 2-5, 2-7 ~ 2-8 | 2-6 | ✅ |
| 4주차 | 3-2 ~ 4-3 | 3-4 | ✅ |
| 5주차 | 4-4 ~ 4-6 | 4-5, 4-7 | ✅ |
| 6주차 | 5-2 ~ 5-5 | 5-6 | 🍽️ |
| 7주차 | 필수 강의 없음 | 6-2, 6-3, 6-4, 6-5 | 🍽️ |

---

<br>

<!-- 여기까진 그대로 둬 주세요-->

---

# 1️⃣ 개념 정리

아래 키워드 중 중요하다고 생각한 개념을 2개 이상 골라 짧게 정리해주세요. 3개보다 더 많이 정리하고 싶다면 자유롭게 항목을 추가해도 좋습니다.

이번 주 키워드:
- DATE
- DATETIME
- TIMESTAMP
- EXTRACT
- DATETIME_TRUNC
- FORMAT_DATETIME
- CASE WHEN
- IF

## 01.

```
개념 이름:시간데이터
개념 설명:
날짜 및 시간 데이터 타입 : DATE,DATETIME,TIMESTAMP
*타입 간 변환이 가능하다
DATE : 날짜만 표시하는 데이터 (ex.2023-12-31)
DATETIME : DATE + TIME (ex.TIME ZONE 정보 없음 2023-12-31 14:00:00)
TIMESTAMP : UTC(과거 GMT, 현재는 UTC 많이 사용)부터 경과한 시간을 나타내는 값 (ex.TIME ZONE 정보 있음 2023-12-31 14:00:00 UTC)
예시 쿼리:
SELECT
CURRENT_DATE()AS current_date,
CURRENT_DATE("Asia/Seoul")AS asia_date,
CURRENT_DATETIME()AS current_datetime,
CURRENT_DATETIME("Asia/Seoul")AS current_datetime_asia;

```

## 02.

```
개념 이름:EXTRACT
개념 설명:DATETIME 에서 특정 부분만 추출하고 싶은 경우
주문이나 주문시간 db에서 일자별 월별 주문을 뽑고 싶다고 할 때 해당 데이터를 월로 치환을 하고 집계할 수 있게 함. 
예시 쿼리:EXTRACT(part FROM datetime_expression)
part 안에는 .. MICROSECOND MILLISECOND SECOND MINUTE HOUR DAYOFWEEK DAY DAYOFYEAR WEEK ISOWEEK MONTH QUATER YEAR ISOYEAR DATE TIME 등이 들어갈 수 있다.
```

## (선택) 03.

```
개념 이름:
개념 설명:
헷갈린 점:
```

---

# 2️⃣ 수행 인증란

아래 중 하나 이상을 첨부해주세요.

![수강인증](https://github.com/jaeyi041113-ops/test/blob/main/%E1%84%8B%E1%85%B5%E1%84%86%E1%85%B5%E1%84%8C%E1%85%B5/0A9E154F-B732-4377-A5A7-79F858A118BB.jpeg)

---

# 3️⃣ 확인 문제

프로그래머스는 로그인이 필요하므로, 로그인 후 문제 풀이를 진행해주세요.

## 🧩 문제 1

문제 링크: [자동차 대여 기록에서 장기/단기 대여 구분하기](https://school.programmers.co.kr/learn/courses/30/lessons/151138)

풀이 과정:

```
- 장기/단기 대여를 나눈 기준:
  대여 기간이 30일 이상이면 '장기 대여', 30일 미만이면 '단기 대여'로 구분했다.

- 사용한 날짜 계산 방식:
  `DATEDIFF(END_DATE, START_DATE)`를 사용해 두 날짜의 차이를 계산했다.
  시작일과 종료일을 모두 대여 기간에 포함해야 하기 때문에 `+ 1`을 해주었다.

- CASE WHEN으로 만든 컬럼:
  `CASE WHEN`을 사용하여 대여 기간이 30일 이상인지 판단하고,
  결과를 '장기 대여' 또는 '단기 대여'로 표시하는 `RENT_TYPE` 컬럼을 만들었다.
```
![문제1](https://github.com/jaeyi041113-ops/test/blob/main/%E1%84%8B%E1%85%B5%E1%84%86%E1%85%B5%E1%84%8C%E1%85%B5/BAEB0E4D-35E1-4ECC-88BC-9F5E57F53563.jpeg)

## 🧩 문제 2

문제 링크: [한 해에 잡은 물고기 수 구하기](https://school.programmers.co.kr/learn/courses/30/lessons/298516)

풀이 과정:

```
- 문제에서 요구한 연도:
  2021년도

- 사용한 날짜 조건:
  `YEAR(TIME) = 2021`을 사용하여 `TIME`에서 연도만 추출하고, 2021년에 잡힌 물고기만 조회했다.

- 집계한 대상:
  `COUNT(*)`을 사용하여 조건에 해당하는 전체 물고기 행의 개수를 세고, 컬럼명을 `FISH_COUNT`로 지정했다.

```

![문제2](https://github.com/jaeyi041113-ops/test/blob/main/%E1%84%8B%E1%85%B5%E1%84%86%E1%85%B5%E1%84%8C%E1%85%B5/2B04F6E3-D8C3-495C-A2AA-11AA11AD405C.jpeg)

## 🧩 문제 3

문제 링크: [조건에 부합하는 중고거래 상태 조회하기](https://school.programmers.co.kr/learn/courses/30/lessons/164672)

풀이 과정:

```
- 날짜 조건:
  `DATE(CREATED_DATE) = '2022-10-05'`를 사용하여 2022년 10월 5일에 등록된 게시물만 조회했다.

- CASE WHEN으로 바꾼 값:
  `SALE`은 '판매중', `RESERVED`는 '예약중', `DONE`은 '거래완료'로 변경했다.

- ELSE에 해당하는 경우:
  문제에서 주어진 거래상태가 SALE, RESERVED, DONE으로 정해져 있기 때문에 별도의 `ELSE`는 작성하지 않았다. 조건에 해당하지 않는 값이 있다면 NULL로 출력된다.

- 정렬 기준:
  `ORDER BY BOARD_ID DESC`를 사용하여 게시글 ID를 기준으로 내림차순 정렬했다.
```
![문제3](https://github.com/jaeyi041113-ops/test/blob/main/%E1%84%8B%E1%85%B5%E1%84%86%E1%85%B5%E1%84%8C%E1%85%B5/16150512-AECC-48E2-B1F8-8B93FDB49025.jpeg)

## 🧩 문제 4

문제 링크: [자동차 평균 대여 기간 구하기](https://school.programmers.co.kr/learn/courses/30/lessons/157342)

풀이 과정:

```
- GROUP BY 기준:
  자동차별 평균 대여 기간을 구해야 하기 때문에 `CAR_ID`를 기준으로 그룹화했다.

- 평균을 계산한 방식:
  `DATEDIFF(END_DATE, START_DATE) + 1`로 각 대여 기록의 실제 대여 일수를 계산하고, `AVG()`를 사용해 자동차별 평균을 구했다.
  시작일과 종료일을 모두 대여 기간에 포함하기 때문에 `+ 1`을 해주었다.
  이후 `ROUND(..., 1)`을 사용해 소수점 둘째 자리에서 반올림했다.

- HAVING에 사용한 조건:
  `AVG(DATEDIFF(END_DATE, START_DATE) + 1) >= 7`을 사용하여 자동차별 평균 대여 기간이 7일 이상인 그룹만 남겼다.

- 처음 헷갈렸던 점:
  평균 대여 기간이 7일 이상인 자동차를 찾는 조건을 `WHERE`에 써야 하는지 `HAVING`에 써야 하는지 헷갈렸다.
  여기서는 `GROUP BY` 후 계산된 평균값을 기준으로 필터링해야 하기 때문에 `WHERE`가 아니라 `HAVING`을 사용해야 한다.
```

![문제4](https://github.com/jaeyi041113-ops/test/blob/main/%E1%84%8B%E1%85%B5%E1%84%86%E1%85%B5%E1%84%8C%E1%85%B5/E47B9227-BF49-4F85-831F-81FAA61FCDCD.jpeg)

---

# 4️⃣ 이번 주 회고

```
1. 날짜 함수 중 가장 헷갈린 함수:
`DATEDIFF`가 가장 헷갈렸다. 두 날짜의 차이만 계산하기 때문에 실제 대여 기간처럼 시작일과 종료일을 모두 포함해야 하는 경우에는 `+1`을 해줘야 한다는 점을 기억해야겠다.

2. CASE WHEN을 사용할 때 기억해야 할 문법:
`CASE WHEN 조건 THEN 결과 ELSE 결과 END`의 구조를 기억해야 한다. 여러 조건이 있다면 `WHEN ~ THEN`을 추가하고, 마지막에 반드시 `END`를 작성해야 한다.

3. 날짜/시간 데이터나 조건문을 활용해보고 싶은 분석 상황:
고객의 서비스 이용 기록을 날짜별로 분석해보고 싶다. 예를 들어 최근 30일 동안 이용한 고객과 장기간 이용하지 않은 고객을 CASE WHEN으로 나누고, 고객별 이용 패턴이나 재방문율에 차이가 있는지 확인해보고 싶다.
```

수고하셨습니다!



