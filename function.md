# 함수 (function)

> 특정기능을 반복해서 수행해야 할 때, 직접 기능을 정의하여 사용하는 것이 함수

- 함수의 기본 구조 
  - 함수를 정의 (def) --> 함수를 호출(함수명) : 
  - def 함수명([인자1,인자2,...,인자n]) : 
- 함수명 : 주로 영문 알파벳 소문자로 구성되며 가독성을 높이기 위해 밑줄(_)이용
- 반환값이 있으면 마지막 줄에 return<반환값>입력함. 
- 인자/반환값도 없는 함수 

```python
def my_func() : 
  print("My first function")
  print("This is a function")
  
my_func()
----
My first function
This is a function
```

- 인자 有, 반환값 無 함수

```python
def my_friend(friendName):
  print("{}는 나의 친구입니다.". format(friendName))
my_friend("영수")
----
영수는 나의 친구입니다.
```

- 인자 有, 반환값 有

```python
def my_calc(x,y):
    z = x * y
    return z 

my_calc(3,4)
----
12
```

- 변수의 유효 범위 
  - 함수안에서 정의한(혹은 생성한) 변수는 함수 안에서만 사용 = 지역변수(local variable)
  - 반대의 개념으로 전역 변수(global variable), 함수 밖에서 생성한 변수 
  - 지역변수를 저장하는 이름 공간을 지역영역 (local scope)
  - 전역변수를 저장하는 이름 공간을 전역영역(global scope)
  - 파이썬 자체에서 정의한 이름 공간을 내장영역(built-in scope)
  - 함수에서 어떤 변수를 호출하면 지역 영역, 전역 영역, 내장 영역 순서대로 변수가 있는지 확인 
  - 스코핑룰(scoping rule) 혹은 LGB 룰 (Local/Global/Built_in rule) 이라고 함. 

```python
a = 5 #전역변수

def func1():
  a = 1 #지역 변수, func1()에서만 사용
  print("[func1] 지역 변수 a=", a)

def func2():
  a = 2 #지역 변수, func2()에서만 사용
  print("[func2] 지역 변수 a=", a)

def func3():
  a = 3 #지역 변수, func2()에서만 사용
  print("[func3] 지역 변수 a=", a)

def func4():
  global a # 함수 내에서 전역 변수 변경 위해 선언
  a = 4 #전역 범수의 값 변경
  print("[func4] 전역 변수 a=", a)

func1()
func2()
print("전역 변수 a=", a)
----
[func1] 지역 변수 a= 1
[func2] 지역 변수 a= 2
전역 변수 a= 5

func3()
func4()
func3()
----
[func3] 지역 변수 a= 3
[func4] 전역 변수 a= 4
[func3] 지역 변수 a= 3
```

