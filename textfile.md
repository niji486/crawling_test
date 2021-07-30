# 문자열과 텍스트 파일 데이터 다루기 

> 문자열 데이터처리 --> 숫자, 문자열의 데이터를 필요없는 문자 제거, 찾기, 연결 등의 전처리하는 것
>
> 파이썬에서는 문자열 처리를 위한 다양한 `내장 문자열 메서드`가 제공되므로 처리하기 쉬움 
>
> `문자열을 처리하는 방법`과 `텍스트 파일의 내용을 읽어서` 처리하는 방법 2가지 

1. 문자열 분리하기 

-  split() 내장함수 메서드를 이용 : str.split([sep])
- 문자열에 인사없이 split()를 사용하면 문자열 사이의 모든 공백과 개행문자(\n)를 없애고 분리된 문자열을 반환 
- maxsplit을 추가하면 앞에서부터 원하는 횟수만큼만 문자열을 분리할 수 있음

```python
coffee_menu_str = "에스프레스, 아메리카노, 카페라떼, 카푸치노"
coffee_menu_str.split(',')
----
['에스프레스', ' 아메리카노', ' 카페라떼', ' 카푸치노'] #리스트로 출력

#직접 인자에 리스트를 입력하여 가능 

"에스프레스, 아메리카노, 카페라떼, 카푸치노".split(',')
→ ['에스프레스', ' 아메리카노', ' 카페라떼', ' 카푸치노']

#split(' ')=split()--> 공백기준,
"에스프레스, 아메리카노, 카페라떼, 카푸치노".split(' ')
→ ['에스프레스,', '아메리카노,', '카페라떼,', '카푸치노']

"에스프레스, 아메리카노, 카페라떼, 카푸치노".split()
→ ['에스프레스,', '아메리카노,', '카페라떼,', '카푸치노']

"      에스프레스 \n\n    아메리카노 \n\n   카페라떼 \n\n   카푸치노 \n\n".split()
→ ['에스프레스', '아메리카노', '카페라떼', '카푸치노']

"에스프레스, 아메리카노, 카페라떼, 카푸치노".split(maxsplit=2)
→ ['에스프레스,', '아메리카노,', '카페라떼, 카푸치노']
```

2. 필요없는 문자열 삭제하기

- strip() 내장 메서드 활용 
- 문자열(str)에서 `앞뒤`에 있는 지정한 문자(chars)만 삭제. (중간에 다른 문자에 섞인 지정문자는 X)

```python
"aaaBallaaa".strip('a')
→ Ball  #Ball의 'a'는 지워지지 않음. 
```

- strip() 으로 적용되면 문자열(str) 앞뒤에 있는 공백/개행문자는 삭제되지만, 문자열 사이에 있는 
  공백/개행문자는 삭제되지 않음. 

```python
"\n This is very \n fast \n\n".strip()
→This is very \n fast  #문장 사이에 \n(개행문자)는 삭제되지 않음
```

- 콤마와 공백을 포함한 문자열에서 콤마를 기준으로 문자열을 분리하고, 공백을 모두 제거
- 3단계로 진행 : step1. split(,)으로 문자열 분리하기 
                           step2.strip()으로 문자열마다 공백 반복제거(for)
                           step3. 새로운 리스트 변수에 공백 제거된 문자열 순차적으로 넣기 

```python
#step 1.
coffee_menu=" 에스프레소, 아메리카오, 카페라떼, 카푸치오 "
coffee_menu_list=coffee_menu.split(',')
coffee_menu_list
→ [' 에스프레소', ' 아메리카오', ' 카페라떼', ' 카푸치오 ']
#step 2.3 
coffee_list = [] #빈 리스트 생성(Step3.)
for coffee in coffee_menu_list:
  temp = coffee.strip() # 문자열의 공백 제거(Step.2)
  coffee_list.append(temp) #리스트 변수에 공백이 제거된 문자열 추가(step.3) 

print(coffee_list) #최종 문자열 리스트 출력
→['에스프레소', '아메리카오', '카페라떼', '카푸치오']
```



3. 문자열 연결하기

- join() 메서드를 이용해 문자열로 변환하는 과정 : stir.join(seq)
- 문자열 리스트의 항목 사이에는 구분자 문자열(한 칸 공백)이 들어감

```python
address_list= ["서울시", "서초구", "반포대로", "201(반포동)"]
address_list
→ ['서울시', '서초구', '반포대로', '201(반포동)']

a = " "
a.join(address_list)
→ '서울시 서초구 반포대로 201(반포동)'

" ".join(address_list)
→ '서울시 서초구 반포대로 201(반포동)'

"☆".join(address_list)
→ '서울시☆서초구☆반포대로☆201(반포동)'
```



4. 문자열 찾기

- find() : str.find(search_str)

```python
str_f = "Python code."
print("찾는 문자열의 위치:", str_f.find("Python"))
print("찾는 문자열의 위치:", str_f.find("code"))
print("찾는 문자열의 위치:", str_f.find("n"))
print("찾는 문자열의 위치:", str_f.find("easy"))
→ 
찾는 문자열의 위치: 0
찾는 문자열의 위치: 7
찾는 문자열의 위치: 5
찾는 문자열의 위치: -1
```



5. 문자열 바꾸기 ☆☆☆☆☆

- replace() : 문자열을 하나씩만 지정할 수 있음  str.replace('As-is str','To-be str' )

```python
str_b = '[Python] [is] [fast]'
str_b1 = str_b.replace('[','')
str_b2 = str_b.replace(']','')

print(str_b)
print(str_b1)
print(str_b2)
→
[Python] [is] [fast]
Python] is] fast]
[Python [is [fast
```

6. 문자열의 구성 확인하기 

- 주어진 메소드의 질문에 맞게 검토 후  맞으면 True, 아니면 False 출력
- isalpha(): 모두 알파벳인지
- isdigit():모두 숫자인지
- isalnum():모두 공백, 특수문자없이 문자숫자만 있는지?
- isspace():모두 공백으로만 구성되어있는지
- isupper():모두 대문자로만 되어있는지
- islower():모두 소문자로만 되어있는지
  - 대소문자로 변경하기 : upper(), lower()







