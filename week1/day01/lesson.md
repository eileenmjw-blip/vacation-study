# Day 1 — 변수/자료형, print/input, VSCode 실행법

## 오늘 배울 것
- 변수에 값 저장하기
- 자료형: 정수(int), 실수(float), 문자열(str), 불리언(bool)
- `print()`로 출력, `input()`으로 입력받기
- 형변환: `int()`, `str()`, `float()`
- VSCode에서 파일 실행하고 에러 읽는 법

## 1. 변수와 자료형

```python
age = 20          # int
height = 165.5    # float
name = "Eileen"   # str
is_student = True # bool

print(age)
print(type(age))  # <class 'int'> 라고 나옴 - 어떤 자료형인지 확인하는 함수
```

`type()`은 값의 자료형을 알려주는 함수입니다. 헷갈릴 때마다 찍어보면 됩니다.

## 2. input()과 형변환

`input()`은 **항상 문자열(str)**을 돌려줍니다. 숫자 계산을 하려면 반드시 변환해야 해요.

```python
age_input = input("나이를 입력하세요: ")  # "20" (문자열!)
age = int(age_input)                      # 20 (숫자로 변환)
print(age + 1)                            # 21
```

이걸 안 하면 이런 일이 생깁니다:
```python
age = input("나이: ")
print(age + 1)
# TypeError: can only concatenate str (not "int") to str
```
→ 지난번 테스트 Q1에서 `int(y)`로 형변환한 게 정확히 이런 상황이었습니다. 잘 하셨어요.

## 3. 문법 규칙: 콜론(`:`)과 들여쓰기

파이썬은 **블록을 시작하는 줄 끝에 반드시 `:`를 붙입니다.** (`if`, `for`, `while`, `def` 전부 해당)
그리고 그 블록 안의 코드는 **들여쓰기(보통 스페이스 4칸)**로 구분합니다.

```python
def greet(name):        # 콜론 필수!
    print("Hello, " + name)   # 들여쓰기로 "이 줄은 함수 안" 표시

greet("Eileen")
```

콜론을 빼먹으면 이렇게 에러가 납니다:
```
  File "day01.py", line 1
    def greet(name)
                   ^
SyntaxError: expected ':'
```
→ 에러 메시지에 `expected ':'` 라고 정확히 나옵니다. 앞으로 이런 에러를 보면 "콜론 빼먹었나?"부터 의심하세요.

## 4. VSCode에서 실행하기
1. `week1/day01/practice.py` 파일을 엽니다
2. 오른쪽 위 ▶ 버튼 클릭 (또는 `F5`, 또는 터미널에 `python week1/day01/practice.py`)
3. 아래쪽에 출력 결과가 뜹니다
4. 에러가 나면 맨 아래 줄(`SyntaxError: ...` 같은 부분)을 먼저 읽고, 몇 번째 줄(line)인지 확인

## 오늘의 핵심 요약
- 변수 = 값에 이름 붙이기
- `input()`은 항상 문자열 → 숫자로 쓰려면 `int()`/`float()` 필요
- 블록을 여는 줄 끝엔 반드시 `:` , 그 안의 코드는 들여쓰기

---
다음: `practice.py`를 열어서 TODO를 채워보세요.
