# 모듈

> 파이썬 코드로 작성된 파일을 다른 파일에서 불러와 이 파일의 변수, 함수, 클래스를 이용할 수 있음.
>
> 이 코드가 저장된 파일을 모듈(Module)이라 부름. 
>
> 이미 만들어진 모듈을 활용하여 코드를 효과적으로 작성. ( 콘솔이나 주피터 노트북에서 실행)



1.  모듈 만들기

- 모듈이름.py 로 저장. 내장마술명령어 (Magic command)인 '%%writefile'을 이용해 코드로 파일저장

```python
%%writefile my_first_module.py  
#File name : my_first_module.py
def my_function(_):
  print("This is my first module")
→ Writing my_first_module.py

!cat my_first_module.py
→
#File name : my_first_module.py
def my_function(_):
  print("This is my first module")

```

2. 모듈 불러오기 

- import 
- 모듈을 임포트 한 후에는 '모듈명.변수()', '모듈명.함수()', 모듈명.클래스()'와 같은 형식으로
  모듈에서 정의한 내용을 사용 

```python
!ls
→ my_first_module.py  sample_data

import my_first_module
my_first_module.my_function()
→ This is my first module
```

```python
%%writefile my_area.py
# File name my_area.py

PI = 3.14
def square_area(a) : 
  return a **2

def circle_area(r) : 
  return PI * r **2
→Writing my_area.py

import my_area
print('pi=', my_area.PI)
print('square area=', my_area.square_area(5))
print('circle area=', my_area.circle_area(2))
→
pi= 3.14
square area= 25
circle area= 12.56

# 똑같은 방법
from my_area import *
print('pi=', my_area.PI)
print('square area=', my_area.square_area(5))
print('circle area=', my_area.circle_area(2))
```



3. 불러온 모듈에서 사용할 수 있는 변수, 함수, 클래스를 알고싶다면 'dir(모듈명)'을 이용

```python
dir(my_area)
→
['PI',
 '__builtins__',
 '__cached__',
 '__doc__',
 '__file__',
 '__loader__',
 '__name__',
 '__package__',
 '__spec__',
 'circle_area',
 'square_area']
```

4. 모듈을 불러오는 다른 형식 

- 모듈 내에 있는 변수, 함수, 클래스를 '모듈명.'없이 직접 호출해서 이용할 수 있음

```python
from my_area import PI, square_area, circle_area #모듈의 변수, 함수 바로 불러오기 
print('pi=', PI)
print('square area=', my_area.square_area(5))
print('circle area=', my_area.circle_area(2))
→
pi= 3.14
square area= 25
circle area= 12.56
```



5. 2개의 모듈에서 불러오기 

- 2개의 모듈을 import * 의 방법으로 모두 불러온다면, 공통으로 있는 함수(Ex., func2)에 대해서는
  나중에 선언해서 불러온(my_module2)의 함수가 호출됨

```python
%%writefile my_module1.py
# File name : my_module1.py

def func1():
  print("func1 in my_module1")

def func2():
  print("func2 in my_module2")
  
%%writefile my_module2.py
# File name : my_module2.py

def func2():
  print("func2 in my_module2")

def func3():
  print("func3 in my_module3")
  
from my_module2 import *
from my_module1 import *
→
func1()
func2()
func3()

func1 in my_module1
func2 in my_module2  ==> 나중에 선언된 my_module2 의 func2 를 가져옴
func3 in my_module3
```

6. 모듈을 직접 수행할때만 실행(run), 임포트했을 때만 실행(import)하게 하는 코드 

- 직접 수행할 때만 실행되는 코드 : if ``__name__``==`"__main__"`
- 임포트됐을때만 실행되는 코드  : else

```python
%%writefile my_module_test3.py
# file name : my_module_test3.py

def func(a) : 
  print("입력숫자:", a)

if __name__ == "__main__" : 
  print("모듈을 직접 실행")
  func(3)
  func(4)
else:
  print("모듈을 임포트해서 실행")

%run my_module_test3.py
→
모듈을 직접 실행
입력숫자: 3
입력숫자: 4
    
import my_module_test3
→ 모듈을 임포트해서 실행
```

