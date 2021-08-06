### (1) 클래스와 객체의 기본 개념 및 생성방법 



> 객체란?
>
> 객체는 속성(상태,특징)과 행위(행동, 동작, 기능)으로 구성된 대상을 의미
>
> 프로그래밍 언어에서는 속성=> 변수, 행위=>함수로 구현, 따라서 객체는 변수와 함수의 묶음
>
> 객체를 만들고 이용할 수 있는 기능을 제공하는 프로그래밍 언어를 
>
> `객체지향 프로그래밍` `(Object-Oriented Programming, OOP)` 혹은 `객체지향 언어`라고 함. 

> 클래스 선언
>
> 객체를 만들려면 먼저 클래스를 선언해야 함 
>
> 클래스가 기본 틀이라면, 객체는 기본 틀을 바탕으로 만들어진 결과임. 
>
> 객체는 클래스에서 생성하므로 객체를 클래스의 `인스턴스` `(Instance)` 라고 함. 

- 클래스 선언을 위한 기본 구조 

```
class 클래스명() : # 보통 로마자 알파벳 `대문자`로 시작하며 여러 단어 연결 
     [변수1] #클래스 변수
     [변수2]
     def 함수1(self[,인자1, 인자2, ..., 인자n]):  #클래스 함수, 첫번째 인자는 self
     <코드블록>
     def 함수2(self[,인자1, 인자2, ..., 인자n]):  #self는 객체 생성 후에 자신을 참조함. 
     <코드블럭>
```

- 클래스 선언 방법

```python
# 자전거 클래스 만들기
# 자전거 클래스를 만들기 전에 우선 자전거가 갖는 속성과 동작을 정의
# 속성(변수) : ex. 바퀴크기(wheel_size, 색상(color)
# 동작(함수) : ex. 이동(move), 좌/우회전(turn), 정지(stop)

class Bicycle():  # 클래스 선언
	pass # 클래스 선언 후 pass 외에 속성/동작 없는 상태이나, 엄연한 클래스임.
	
my_bicycle = Bicycle() # 자전거 클래스 내에 객체 생성 
my_bicycle
→ <__main__.Bicycle at 0x7f39c0cef950>  
#객체를 실행하면 생성할 때 할당받은 메모리의 주소값을 출력함.
# 출력 결과에서 my_bicycle 객체의 클래스는 Bicycle임을 확인할 수 있음 
```

- 클래스에서 객체 생성

```python
my_bicycle = Bicycle() # 자전거 클래스 내에 객체 생성 
my_bicycle
→ <__main__.Bicycle at 0x7f39c0cef950>  
#객체를 실행하면 생성할 때 할당받은 메모리의 주소값을 출력함.
# 출력 결과에서 my_bicycle 객체의 클래스는 Bicycle임을 확인할 수 있음 
```

- 객체에 속성값을 설정

```python
my_bicycle.wheel_size = 26 #생성한 my_bicycle 객체에 속성값을 설정.
my_bicycle.color = 'black'
print("바퀴크기 :", my_bicycle.wheel_size) # 객체의 속성 출력
print("색상:", my_bicycle.color)
→
바퀴크기 : 26
색상: black
```

- 클래스에 함수 추가 

```python
#선언한 Bicycle 클래스에 함수 추가 
# 속도 move, 좌/우회전 turn, 정지 stop

class Bicycle() : 

  def move(self, speed) : 
    print("자전거 : 시속 {0}킬로미터로 전진".format(speed))

  def turn(self, direction) : 
    print("자전거 : {0}회전".format(direction))
  
  def stop(self):
    print("자전거({0},{1}) : 정지".format(self.wheel_size, self.color))
```

- 자전거 클래스 --> 객체 생성 --> 속성 설정 --> 메서드 호출

```python
my_bicycle = Bicycle() 

my_bicycle.wheel_size = 26
my_bicycle.color = 'black'

my_bicycle.move(30)
my_bicycle.turn('좌')
my_bicycle.stop()
→
자전거 : 시속 30킬로미터로 전진
자전거 : 좌회전
자전거(26,black) : 정지
```

- 객체 초기화 
  - Bicycle 클래스를 선언할 때 초기화함수 `__int__()`을 구현하면
    객체를 생성하는 것과 동시에 속성값을 지정할 수 있음.

```python
class Bicycle() : 

  def __init__(self, wheel_size, color):
    self.wheel_size = wheel_size    # 객체 생성과 동시에 속성값을 지정 
    self.color = color

  def move(self, speed) : 
    print("자전거 : 시속 {0}킬로미터로 전진".format(speed))

  def turn(self, direction) : 
    print("자전거 : {0}회전".format(direction))
  
  def stop(self):
    print("자전거({0},{1}) : 정지".format(self.wheel_size, self.color))
    
my_bicycle = Bicycle(26, 'black')  # 객체 생성과 동시에 속성값을 지정 

my_bicycle.move(30)
my_bicycle.turn('좌')
my_bicycle.stop()
→
자전거 : 시속 30킬로미터로 전진
자전거 : 좌회전
자전거(26,black) : 정지

# 위 코드와 비교시, my_bicycle.wheel_size = 26, my_bicycle.color = 'black' 필요없음.
```

