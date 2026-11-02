# 📘 SQL_BASIC 6주차 정규 과제

SQL_BASIC 정규 과제는 매주 정해진 분량의 `초보자를 위한 BigQuery(SQL) 입문` 강의를 듣고, 핵심 개념을 정리한 뒤 간단한 SQL 문제를 직접 풀어보는 방식으로 진행합니다.

이번 주는 SQL 입문 과정의 핵심 고비인 `JOIN`을 학습합니다.

JOIN은 여러 테이블을 연결해서 분석 질문에 답하기 위해 반드시 필요한 개념입니다. 이번 주 과제에서는 정답 코드뿐 아니라 **어떤 테이블을 어떤 키로 연결했는지**를 꼭 기록해주세요.

완성된 과제는 Github에 업로드하고, 링크를 스프레드시트 'SQL' 시트에 입력해 제출해주세요.

**👀 수행 인증란은 필수입니다.**

---

## 📚 SQL_BASIC_6th_TIL

### 섹션 6. 다량의 자료를 연결 : JOIN

### 5-2. JOIN 이해하기

### 5-3. 다양한 JOIN 방법

### 5-4. JOIN 쿼리 작성하기

### 5-5. JOIN을 처음 공부할 때 헷갈리는 부분

---

## ✨ 선택 강의

- 5-6. JOIN 연습문제: JOIN 문제를 더 연습하고 싶을 때 선택 수강

---

## 🏁 전체 강의 수강 계획

| 주차 | 필수 강의 범위 | 선택 강의 | 완료 여부 |
| --- | --- | --- | --- |
| 1주차 | 1-1 ~ 2-1 | 1 | ✅ |
| 2주차 | 2-2 ~ 2-3 | 2-4 | ✅ |
| 3주차 | 2-5, 2-7 ~ 2-8 | 2-6 | ✅ |
| 4주차 | 3-2 ~ 4-3 | 3-4 | ✅ |
| 5주차 | 4-4 ~ 4-6 | 4-5, 4-7 | ✅ |
| 6주차 | 5-2 ~ 5-5 | 5-6 | ✅ |
| 7주차 | 필수 강의 없음 | 6-2, 6-3, 6-4, 6-5 | 🍽️ |

---

<br>

<!-- 여기까진 그대로 둬 주세요-->

---

# 1️⃣ 개념 정리

아래 키워드 중 중요하다고 생각한 개념을 2개 이상 골라 짧게 정리해주세요. 3개보다 더 많이 정리하고 싶다면 자유롭게 항목을 추가해도 좋습니다.

이번 주 키워드:
- JOIN
- INNER JOIN
- LEFT JOIN
- JOIN key
- alias
- NULL
- 다중 JOIN

## 01.

```
개념 이름:JOIN
개념 설명:두 개 이상의 테이블을 공통된 KEY값을 기준으로 연결하는 것

하나의 테이블에 없는 정보를 다른 테이블에서 가져와 함께 분석할 때 사용

주로 ID와 같은 공통 컬럼을 기준으로 연결함

JOIN을 하면 기존 테이블에 다른 테이블의 컬럼을 추가할 수 있음

여러 테이블을 한 번에 연결할 수도 있지만, 순서대로 JOIN하면서 결과를 확인하는 것이 좋음

데이터 분석에서는 필요한 정보가 여러 테이블에 나누어져 있는 경우가 많아 자주 사용됨
예시 쿼리:SELECT
    A.COL1,
    A.COL2,
    B.COL11,
    B.COL12
FROM table1 AS A
LEFT JOIN table2 AS B
    ON A.KEY = B.KEY;
```

## 02.

```
개념 이름: NULL
개념 설명:데이터에 값이 존재하지 않거나, 어떤 값인지 알 수 없는 상태를 의미함

숫자 0이나 빈 문자열('')과는 다르게 값 자체가 없다는 뜻

JOIN을 사용할 때 두 테이블에서 일치하는 데이터가 없으면 NULL이 발생할 수 있음

특히 LEFT JOIN은 왼쪽 테이블의 데이터를 모두 유지하기 때문에, 오른쪽 테이블에 연결되는 값이 없으면 해당 컬럼이 NULL로 표시됨

NULL은 일반적인 비교 연산자(=) 대신 IS NULL이나 IS NOT NULL을 사용해 확인해야 함
예시 쿼리:SELECT *
FROM table1
WHERE COL1 IS NULL;
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

![수강](https://github.com/jaeyi041113-ops/test/blob/main/%E1%84%8B%E1%85%B5%E1%84%86%E1%85%B5%E1%84%8C%E1%85%B5/FF75D6B0-D2F5-4551-AF98-34BD58966386.jpeg)

---

# 3️⃣ 확인 문제

프로그래머스는 로그인이 필요하므로, 로그인 후 문제 풀이를 진행해주세요.

## 🧩 문제 1

문제 링크: [조건에 맞는 도서와 저자 리스트 출력하기](https://school.programmers.co.kr/learn/courses/30/lessons/144854)

풀이 과정:

```
- 사용한 테이블: BOOK, AUTHOR
- JOIN key: AUTHOR_ID
- 날짜를 출력한 형식: YYYY-MM-DD
```

![1](https://github.com/jaeyi041113-ops/test/blob/main/%E1%84%8B%E1%85%B5%E1%84%86%E1%85%B5%E1%84%8C%E1%85%B5/91E9D1D0-07B3-4BF4-AC37-D9A3DA6B8C59.jpeg)

## 🧩 문제 2

문제 링크: [상품 별 오프라인 매출 구하기](https://school.programmers.co.kr/learn/courses/30/lessons/131533)

풀이 과정:

```
- 연결한 테이블: PRODUCT, OFFLINE_SALE
- JOIN key: PRODUCT_ID
- 집계한 값: 상품코드별 매출액 합계 (판매가 * 판매량)
```

![2](https://github.com/jaeyi041113-ops/test/blob/main/%E1%84%8B%E1%85%B5%E1%84%86%E1%85%B5%E1%84%8C%E1%85%B5/CA704232-CE1E-467F-8FF0-4F08F974EDEF.jpeg)

## 🧩 문제 3

문제 링크: [없어진 기록 찾기](https://school.programmers.co.kr/learn/courses/30/lessons/59042)

풀이 과정:

```
- 기준이 되는 왼쪽 테이블: ANIMAL_OUTS
- LEFT JOIN이 필요한 이유: 입양 기록은 모두 유지하면서 보호소에 들어온 기록이 없는 동물을 찾기 위해
- NULL이 발생하는 경우: ANIMAL_OUTS에는 있지만 ANIMAL_INS에는 일치하는 ANIMAL_ID가 없는 경우
```

![3](https://github.com/jaeyi041113-ops/test/blob/main/%E1%84%8B%E1%85%B5%E1%84%86%E1%85%B5%E1%84%8C%E1%85%B5/27E39A96-EF0E-4239-BB24-53F09F3C93F1.jpeg)

## 🧩 문제 4

문제 링크: [있었는데요 없었습니다](https://school.programmers.co.kr/learn/courses/30/lessons/59043)

풀이 과정:

```
- 기준이 되는 왼쪽 테이블: ANIMAL_OUTS
- LEFT JOIN이 필요한 이유: 입양 기록은 모두 유지하면서 보호소에 들어온 기록이 없는 동물을 찾기 위해
- NULL이 발생하는 경우: ANIMAL_OUTS에는 있지만 ANIMAL_INS에는 일치하는 ANIMAL_ID가 없는 경우
```

![4](https://github.com/jaeyi041113-ops/test/blob/main/%E1%84%8B%E1%85%B5%E1%84%86%E1%85%B5%E1%84%8C%E1%85%B5/9743DD08-FCFB-42C2-95C7-1F59656EE7F8.jpeg)

---

# 4️⃣ 참고 자료

JOIN 개념이 헷갈린다면 아래 자료를 함께 참고해도 좋습니다.

1. https://data-marketing-bk.tistory.com/entry/SQL-JOIN-%ED%95%9C-%EB%B0%A9%EC%97%90-%EC%A0%95%EB%A6%AC-%EA%B0%9C%EB%85%90%EB%B6%80%ED%84%B0-%EC%BD%94%EB%93%9C%EA%B9%8C%EC%A7%80-%EC%9D%B4%EA%B2%83%EB%A7%8C-%EB%B3%B4%EC%9E%90
2. https://velog.io/@wijoonwu/JOIN

---

# 5️⃣ 이번 주 회고


```
1. INNER JOIN과 LEFT JOIN의 차이를 어떻게 이해했는지:
INNER JOIN은 두 테이블에서 공통된 KEY값이 일치하는 데이터만 가져오고, LEFT JOIN은 왼쪽 테이블의 데이터를 모두 유지한다는 차이가 있다. LEFT JOIN에서는 오른쪽 테이블에 일치하는 값이 없으면 NULL로 표시된다.

2. JOIN 문제를 풀 때 가장 먼저 확인해야 할 것:
어떤 테이블을 연결해야 하는지, 두 테이블에서 공통으로 사용하는 KEY값이 무엇인지 먼저 확인해야 한다. 특히 LEFT JOIN을 사용할 때는 어떤 테이블을 기준으로 할지 정하는 것이 중요하다고 생각했다.

3. JOIN 결과가 예상과 달랐던 경험이 있다면:
입양 기록은 있지만 보호소에 들어온 기록이 없는 동물을 찾는 문제에서 처음에는 INNER JOIN을 사용해도 된다고 생각했다. 하지만 INNER JOIN은 일치하는 데이터만 가져오기 때문에, LEFT JOIN으로 전체 입양 기록을 유지하고 NULL인 값을 찾아야 한다는 점을 이해했다.

수고하셨습니다!



