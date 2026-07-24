# Day 2 — 조건문(if/elif/else), 비교·논리 연산자

## 오늘 배울 것
- 비교 연산자: `==`, `!=`, `>`, `<`, `>=`, `<=`
- 논리 연산자: `and`, `or`, `not`
- `if` / `elif` / `else` 구조
- 자주 하는 실수: `=`(대입)와 `==`(비교) 헷갈림

## 1. 비교 연산자 → 결과는 항상 True/False

```python
print(5 == 5)   # True
print(5 == "5") # False (숫자와 문자열은 값이 같아 보여도 다른 타입)
print(5 != 3)   # True
print(5 > 3)    # True
```

**중요:** Day 1에서 `=`(대입)과 `:`(콜론)을 헷갈리셨었죠. 오늘 또 하나 조심할 게 생겼어요.
- `=` → "값을 저장해라" (대입)
- `==` → "두 값이 같은지 비교해라" (비교, 결과는 True/False)

```python
x = 5     # 대입: x에 5를 저장
x == 5    # 비교: x가 5와 같은지 확인만 함 (저장 안 됨)
```
`if` 조건 안에서는 항상 `==`를 씁니다. `if x = 5:` 라고 쓰면 `SyntaxError`가 납니다.

## 2. if / elif / else

```python
score = 85

if score >= 90:
    print("A")
elif score >= 80:
    print("B")
elif score >= 70:
    print("C")
else:
    print("F")
```
- 위에서부터 순서대로 조건을 검사하다가, **처음으로 참(True)인 조건**의 블록만 실행하고 끝냅니다.
- `if`, `elif`, `else` 모두 줄 끝에 `:` 필요, 그 안쪽은 들여쓰기.
- `elif`는 없어도 되고, 여러 개 있어도 됩니다. `else`는 있어도 되고 없어도 됩니다.

## 3. 논리 연산자: and, or, not

```python
age = 21
has_ticket = True

if age >= 19 and has_ticket:
    print("입장 가능")

if age < 10 or age >= 65:
    print("할인 대상")

if not has_ticket:
    print("티켓이 없습니다")
```
- `and`: 양쪽 다 참이어야 참
- `or`: 둘 중 하나만 참이어도 참
- `not`: 참/거짓을 뒤집음

## 4. 중첩 if (if 안에 if)

```python
if age >= 19:
    if has_ticket:
        print("입장 가능")
    else:
        print("티켓을 구매하세요")
else:
    print("미성년자는 입장 불가")
```
안쪽 `if`는 바깥 `if`보다 들여쓰기가 한 단계 더 들어갑니다.

## 오늘의 핵심 요약
- `==`는 비교, `=`는 대입 (절대 헷갈리면 안 됨)
- `if/elif/else`는 위에서부터 순서대로 검사, 맨 처음 참인 곳만 실행
- `and`/`or`/`not`으로 여러 조건 합치기

---
다음: `practice.py`를 열어서 TODO를 채워보세요.
