# Day 3 — 반복문 (for / while)

## 오늘 배울 것
- `for` 반복문과 `range()`
- `while` 반복문
- `break`(반복 중단)와 `continue`(다음 반복으로 건너뛰기)
- 반복문 안에서 값을 누적하기 (합계, 개수 세기)

어제까지는 코드가 위에서 아래로 한 번씩만 흘렀어요. 오늘부터는 **같은 코드를 여러 번 반복**시킬 수 있습니다. 프로그래밍이 강력해지는 지점이에요.

## 1. for + range()

`range(n)`은 0부터 n-1까지의 숫자를 순서대로 만들어줍니다.

```python
for i in range(5):
    print(i)
# 출력: 0 1 2 3 4  (각각 한 줄씩)
```
- `i`는 반복할 때마다 0, 1, 2, 3, 4로 **자동으로 바뀌는 변수**예요. (이름은 자유지만 보통 i를 씀)
- `range(5)`는 **5를 포함하지 않아요.** 0~4까지 5개. 이거 자주 헷갈리니 주의!

`range`는 시작·끝·간격도 정할 수 있어요:
```python
range(1, 6)      # 1, 2, 3, 4, 5   (1부터 6 직전까지)
range(0, 10, 2)  # 0, 2, 4, 6, 8   (0부터 2씩 증가)
```

## 2. 리스트를 for로 순회하기

```python
fruits = ["apple", "banana", "cherry"]
for fruit in fruits:
    print(fruit)
# apple, banana, cherry 가 각각 한 줄씩
```
`fruit`에 리스트 원소가 하나씩 순서대로 들어옵니다.

## 3. 값 누적하기 (아주 중요!)

반복문에서 가장 많이 쓰는 패턴이에요. **반복문 밖에서 변수를 먼저 만들어두고**, 반복문 안에서 그 변수에 계속 더합니다.

```python
total = 0                 # ① 반복 시작 전에 0으로 준비
for i in range(1, 11):    # ② 1부터 10까지
    total = total + i     # ③ total에 i를 계속 누적 (total += i 라고 써도 됨)
print(total)              # 55
```
> 💡 `total = total + i`는 "지금 total 값에 i를 더한 걸, 다시 total에 저장" 이라는 뜻이에요.
> 첫 진단 테스트 때 `result = x`라고 덮어써서 값이 안 쌓였던 것 기억나시나요? 그때 필요했던 게 바로 이 누적 패턴이에요.

## 4. while 반복문

`for`가 "정해진 횟수"라면, `while`은 **"조건이 참인 동안 계속"** 반복해요.

```python
count = 1
while count <= 5:
    print(count)
    count = count + 1     # ← 이게 없으면 무한 반복! 꼭 조건을 바꿔줘야 함
```
**주의:** `while`은 조건을 언젠가 거짓으로 만들어주지 않으면 **영원히 멈추지 않아요(무한루프).** 위에서 `count`를 1씩 늘려서 언젠가 5를 넘게 만드는 게 핵심이에요.
(무한루프에 빠지면 터미널에서 `Ctrl + C`로 강제 종료할 수 있어요.)

## 5. break와 continue

```python
for i in range(1, 11):
    if i == 5:
        break         # i가 5가 되면 반복 자체를 즉시 종료
    print(i)
# 출력: 1 2 3 4

for i in range(1, 6):
    if i == 3:
        continue      # i가 3일 때는 print를 건너뛰고 다음 반복으로
    print(i)
# 출력: 1 2 4 5  (3만 빠짐)
```
- `break`: 반복문을 완전히 빠져나감
- `continue`: 이번 회차만 건너뛰고 다음 회차로

## 오늘의 핵심 요약
- `for i in range(n)`: n번 반복 (0부터 n-1까지, n은 미포함)
- 값 누적: 반복문 **밖에서** 변수 준비 → 안에서 계속 더하기
- `while 조건:`: 조건이 참인 동안 반복, 조건을 바꿔주지 않으면 무한루프
- `break`=완전 종료, `continue`=한 번 건너뛰기

---
다음: `practice.py`를 열어서 TODO를 채워보세요.
