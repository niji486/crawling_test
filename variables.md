# Python Variables (변수)

> 변수 : 자료를 넣을 수 있는 상자인 변수, 파이썬에서 지원하는 자료형(데이터 타입)
>
> 숫자와 같은 자료(Data)를 넣을 수 있는 상자를 변수(Variables)라 하고 상자에 붙인 이름을 변수명( 혹은 변수 이름)
>
> 실제로 변수는 컴퓨터의 임시 저장 공간(메모리)에 저장 
>
> 

- 변수 사용법 
  - 타입 선언  : ex. `int`(정수형) `a`(변수) --> 하지만, 최근에는 자동 분별함(R, Python)
  - 값 대입(=, 대입연산자, 등호) : `변수명=data` ex. `a=10`

- 변수명 작성 규칙 
  - 문자, 숫자, 밑줄 기호(_)를 이용해 만듦
  - 숫자와 밑줄 기호로 시작하는 변수명을 만들 수 없음
  - 대소문자 구분 - Money != money
  - 공백을 포함할 수 없음 
  - 예약어(Reserved workd)는 사용할 수 없음 
    - None, True, False, and, as, assert, break, class, continue, def, del, elif, else, except, finally , for, from, global, if, import, in, is, lambda, nonlocal, not, or, pass, raise, return, try, while, with, yield

 

# Python String(문자열)

> 문자열로 변수 저장시 `abc='apple'` 컴퓨터는 a.p.p.l.e.10(끝)으로 저장--> Character의 연결=string 

- 문자열 규칙
  - 문자열 안에 큰따옴표를 포함하려면 문자열을 작은따옴표로 감싸고,
    작은 따옴표를 포함하려면 큰타옴표로 감싸면 됨. 
  - 문자열에 큰따옴표, 작은따옴표를 모두 포함하고 싶거나, 문장을 여러행 넣고 싶을 경우, 
    문자열 전체를 삼중 큰따옴표/작은따옴표(""", ''')

```python
[] string3 = 'this is a "double" quotation test.'
[] long_string3='''[삼중 따옴표를 사용한 예]'''
   print(long_string3)
```



> 문자열에는 연산자 더하기(+), 곱하기(*)를 이용할 수 있음 (concatenation)

```python
[] a='Enjoy '
	b='python! '
	c= (a + b) * 3
	print(c)
--> Enjoy python! Enjoy python! Enjoy python! 
```

# Python List(리스트)

- 개요
  - 리스트 [1,2,3,4,5...], ['apple', 'orange'...] `(순서有), 0번째부터 시작)`
  - 튜플 (1,2,3,4,5...)  `(순서有)`
  - 딕셔너리(Dict) { key:value, key;value ...} `(순서無이나, key1,2,3로 구분함)`
  - 세트(Set) {집합들끼리의 연산}
  - Python에서는 주로 리스트, 튜플, 딕셔너리를 가장 많이 사용함



> 리스트(List) : 순자, 문자열, Bool 등의 데이터를 묶어 놓아 관리 및 처리하는 기능 
>
> 예를 들면, 학교에서 학생의 과목별(국어, 영어, 수학, 과학 등) 시험 점수를 처리하거나 학급별로 학생의 이름을 지정할 때 데이터를 묶어서 관리하면 편리함. 

- 리스트 규칙
  - 리스트는 대괄호 []를 이용해, 다양한 데이터 타입 지원
  - 숫자, 문자열, 불, 리스트, 튜플, 셋트, 딕셔너리 등 모두 넣을 수 있음
  - 리스트에서 각 항목은, 변수명[i]로 지정할 수 있음. 여기서 i를 index(인덱스)라고 함.  
  - 리스트를 만들 때 각 항목의 데이터 타입은 같지 않아도 됨. [1, 'Apple', [1,2,3]] (가능)
  - 입력한 순서대로 지정되면 항목은 콤마(,)로 구분
  - 공백은 데이터로 인식하지 않음(아스키코드로 별도 지정필요)
  - 만약 N개의 항목이 있는 리스트 타입의 데이터가 있다면 인덱스 i의 범위는 `0부터 'N-1'`까지임.
  - 첫번째 요소는 `변수명[0]`, 두번째 요소는 `변수명[1]`, 마지막 요소는 `변수명[N-1]`이됨
  - 마지막 요소는 `변수명[-1]`로도 지정할 수 있음. `변수명[N-1]==변수명[-1]`

```python
student1=[90,95,85,80]
-------- -------------
변수명    리스트타입(정수) 
type(student1)=list
student1[0]=90
student1[1]=95
student1[-1]=80
```

- 리스트 내 변경

- 숫자, 문자열, bool, 리스트를 혼합한 형태의 리스트
- 리스트도 더하기(+)와 곱하기(*)를 할 수 있음.

```python
#리스트내 변경 변수명[i]=new_data
student1[1]=100
studen1=[90,100,85,80]
#숫자,문자열,bool, 리스트를 혼합한 
[]mixedList=[0,2,3.14,'python','program',True,student1]
mixedList=[0,2,3.14,'python','program',[90,100,85,80]]
```

- `[중요]` 리스트 중 일부 항목 가져오기 : list[i]
- 범위 가져오기 : list [ i_start`시작` : i_end`끝` : i_step`간격` ]
  i-end는 실제 순서가 아닌 N-1로 인지해야함.
  i-star가 생략되면 0으로 간주, i-end가 생각되면 끝까지로 간주

```python
[] list_data=[0,1,2,3,4,5,6,7,8,9]
   print(list_data)=[0,1,2,3,4,5,6,7,8,9]
   print(list_data)[0:3]=[0,1,2]
   print(list_data)[4:8]=[4,5,6,7]
   print(list_data)[:3]=[0,1,2]
   print(list_data)[7:]= [7,8,9]
 # i_step 사례
   print(list_data)[0::2]=[0,2,4,6,8]
```

- 리스트에서 항목 삭제하기 : del list[i]

```python
[] print(list_data)
   del list_data[6]
   print(list_data)=[0,1,2,3,4,5,7,8,9]
```

- 리스트에서 항목이 존재하는지 여부 확인하기 : index in list

```python
[] list_data1=[1,2,3,4,5]
   print(5 in list_data1)=true
   print(6 in list_data1)=false
```

- 리스트 메서드(List Method) 활용하기, 특정class안에 있기에 함수라기보단 method라 칭함. 
  - 파이썬에서는 데이터타입(자료형)별로 이용할 수 있는 다양한 함수를 제공 --> Method
    - list.method()

```python
list_data1.append(6)=[1,2,3,4,5,6] # 맨 마지막에 추가 
list_data1.insert(1,1.5)=[1,1.5,2,3,4,5] # 호출된 순서에 indext추가
list_data1.extent(7,8)=[1,2,3,4,5,6,7] #항목 여러개를 마지막에 추가 
list_data1.remove(2)=[1,3,4,5]
list_data1.pop()=[1,2,3,4]
list_data1.index(1)=2
list_data1.count(3)=1
list_data1.sort()=[1,2,3,4,5] #숫자, 문자열 혼용시 안되며, 문자열로 통일하거나, 영문 character로.
list_data1.reverse()=[5,4,3,2,1]
```

# Python Tuple(튜플)

> 리스트와 유사하게 데이터 여러 개를 하나로 묶는데 이용하나, 한번 생성되면 항목을 변경할 수 X
>
> 고정되어 있기 때문에 처리속도를 획기적으로 빠르게 할 수 있음. 
>
> 리스트는 []. 튜플은 ()

# Python Dictionary(딕셔너리)

> 사전과 유사하게 구성 키(key):값(value), 항상 쌍으로 구성 

- 리스트, 튜플은 index를 이용해 항목을 다뤘지만, (순서를 자동으로 지정)
- 딕셔너리는 인덱스 대신 키를 이용해 값을 다룸 (key에서 순서를 지정함)
- {key1:value, key2:value,...} 키는 임의로 지정한 숫자나 문자열이 될 수 있음(JSON형식)
- 딕셔너리는 {}, 세트도{}

```python
dictname={key1:value, key2:value, key3:value}
country_capital={'영국':'런던', '스페인'='마드리드'}
type(country_capital)=dict
country_capital['영국']=런던
```

- 키key는 숫자의 문자열이 될 수 있고, 값은 어떤 데이터 형태(list, tuple, dictionary)도 올 수 있음 

