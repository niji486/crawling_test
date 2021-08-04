# 모듈 (2. 내장모듈)

> Python library  에 이미 내장된 모듈, https://docs.python.org/3.9/librar



(1) 난수 발생 모듈

- 코드에서는 정해진 숫자가 아닌 실행할 때마다 임의의 숫자(난수, random number)를 사용해야 할 때.
- 1) 모듈을 먼저 볼러옴 : import random
  2) 함수를 이용 : random.모듈함수() 
- 모듈함수 
  - random : 임의의 실수값
  - randint : 임의의 정수값, or randint(1,6) 1~6까지의 정수 랜덤 
  - randrange : 지정된 범위, 지정된 간격 조건 하에 정수 랜덤 
  - choice : 시퀀스(리스트, 튜플) 데이터에서 랜덤으로 선택 
  - sample : 시퀀스(리스트, 튜플) 데이터에서 정해진 갯수만큼 중복없이 선택하고 싶을 때

```python
import random #random :모듈명
random.random() # random(): 함수, 0~1사이의 임의의 실수를 발생시키는 함수 
→ 0.8499472842356581
→ 0.851558364272969  #실행할 때마다 새로운 실수 출력
```

```python
import random
dice1 = random.randint(1,6) #dice1,2 : 정의된 변수, randit() 모듈함수, 랜덤정수
dice2 = random.randint(1,6)
print('주사위 두개의 숫자 : {0}, {1}'.format(dice1, dice2))
→ 주사위 두개의 숫자 : 3, 6
  주사위 두개의 숫자 : 4, 1
```

```python
import random
num1=random.randrange(1,10,2) #1~9 중 임의의 홀수 선택 
num2=random.randrange(0, 100, 10)  #0~99 중 임의의 10 단위 숫자 선택 
print('num1:{0}, num2:{1}'.format(num1, num2))
→ num1:7, num2:20
  num1:1, num2:90      
```

```python
import random
menu = ['비빔밥', '된장찌개', '볶음밥', '불고기', '스파게티']
random.choice(menu) # 리스트에서 랜덤 선택
→ '불고기'
random.sample([1,2,3,4,5],2) # 모집단에서 두 개의 인자 선택
→ [4,1]
random.sample(['비빔밥', '된장찌개', '볶음밥', '불고기', '스파게티'],2) 
→ ['스파게티', '불고기']
```



(2) 날짜 및 시간 관련 처리 모듈

- 날짜와 시간을 다룰 수 있는 파이썬 내장 모듈 datetime
- 클래스 종류 : 날짜(date), 시간(time), 날짜/시간(datetime)
- 객체를 생성해 이용하는 방법 

```python
#import datetime
#date_obj(변수)=datatime(모듈명).date(클래스)(year,month,day)
#time_obj(변수)=datatime(모듈명).time(클래스)(hour, minute, second)
#datetime_obj(변수)=datatime(모듈명).datetime(클래스)(year,month,day, hour, minute, second)
#datetime_obj(변수)=datatime(모듈명).datetime(클래스).today()

import datetime
set_day=datetime.date(2021,8,2)
print(set_day)
→ 2021-08-02  #내장된 날짜 서식에 맞춰 출력 

print('{0}/{1}/{2}'.format(set_day.year, set_day.month, set_day.day))
→ 2021/8/2 #원하는 서식으로 출력하고 싶은 경우. date클래스의 속성(year,month,day)을 이용

import datetime
set_day2=datetime.datetime.today()
print(set_day2)
→ 2021-08-04 02:21:03.207939 #오늘 날짜이 datetime 서식
        
import datetime
now = datetime.datetime.now()
print(now)
→ 2021-08-04 02:49:26.867295
```

- 날짜/시간 관련 연산 

```python
import datetime

day1=datetime.date(2021,4,1)
day2=datetime.date(2021,7,10)
diff_day=day2 - day1
print(diff_day)
→ 00 days, 0:00:00
        
type(day1)
→ datetime.date #클래스로 출력

type(diff_day)
→ datetime.timedelta # 데이터 타입으로 변경

print("** 지정된 두 날짜의 차이는 {}입니다".format(diff_day.days))
→ ** 지정된 두 날짜의 차이는 100입니다   #days 속성 이용
```

