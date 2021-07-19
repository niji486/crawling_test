# 파이썬 연산 

[#파이썬](https://blog.naver.com/PostListByTagName.naver?blogId=infp_joanne&encodedTagName=파이썬) [#Python](https://blog.naver.com/PostListByTagName.naver?blogId=infp_joanne&encodedTagName=Python) 장점

(1) 가독성 : 문법이 간결하다 (키워드 27개), 들여쓰기로 문단 구분(기본적으로 4칸)

(2) 확장성 : 풍부한 라이브러리

(3) 접착성 : C, JAVA 와 함께 작업할 수 있는 모듈 사용 

(4) 유니코드 : 문자열 유니코드(특히, 한글) 인식  가능 



[#파이썬](https://blog.naver.com/PostListByTagName.naver?blogId=infp_joanne&encodedTagName=파이썬) [#Python](https://blog.naver.com/PostListByTagName.naver?blogId=infp_joanne&encodedTagName=Python) 코딩 규칙 

(1) 들여쓰기 : 조건문 <br> 실행문일때 4칸 공백넣기(들여쓰기)하여 가독성 증대  

(2) 공백x : 표현식, 문장, 괄호 내 공백 X ex. 1+1,[],{}, ;, : --> 컴퓨터는 공백도 데이터로 인식. 제거해서 속도향상

(3) 주석 : # 으로 시작 



[#파이썬](https://blog.naver.com/PostListByTagName.naver?blogId=infp_joanne&encodedTagName=파이썬) [#Python](https://blog.naver.com/PostListByTagName.naver?blogId=infp_joanne&encodedTagName=Python) 프로그램시 중요사항

(1) 명령어, 집합에 대한 문법 학습 필요  

(2) 순차적 명령어 구현 : 실행의 순서에 맞게 정렬하는 것이 중요. interpreter 식이라 1줄씩!



[#파이썬](https://blog.naver.com/PostListByTagName.naver?blogId=infp_joanne&encodedTagName=파이썬) [#데이터처리](https://blog.naver.com/PostListByTagName.naver?blogId=infp_joanne&encodedTagName=데이터처리) 관련 문법 종류

--- 기본 ---

(1) 변수(실수, 상수, 점수, 변수...) 및 자료형(=배열, 리스트, Dictionary)  --> 프로그램 레이아웃의 핵심

(2) 제어문 (조건문, 반복문)

(3) 입력과 출력하는 방법

(4) 함수 

(5) 객체와 클래스(객체지향언어, 객체를 행동으로 표현하는 방법)

(6) 파일 내 문자열, 텍스트 read, write

--- 응용 ---

(7) 데이터분석을 위한 패키지 : numPy, pandas

(8) 시각화 방법 



[#파이썬](https://blog.naver.com/PostListByTagName.naver?blogId=infp_joanne&encodedTagName=파이썬) 사칙연산 관련 써머리 

(1) 연산자 : 덧셈(+), 뺄셈(-), 곱하기(*), 나누기(/)

(2) 수의 종류 

\- 정수(Int) : 자연수(1,2,3...와 자연수의 음수, 그리고 0을 이뤄진 수의 집합

\- 실수(Float) : 유리수와 무리수의 이뤄진 집합, 소수점이 없으면 정수,소수점이 있으면 실수

\- 실수형 --> 실수형, 정수형--> 정수형으로 귀결되나, 파이썬에서 나눗셈 연산은 실수로 출력함.

\- 함수로써도 쓰임. Int('수', 진법)=정수로 출력 ex. int("0b100101", 2) -> 37

(3) 연산 우선순위 : 알고 있는 산수상식과 동일

\- ( ) 괄호

\- 지수계산(**) 

\- 곱셉과 나눗셈

\- 덧셈과 뺄셈



[#파이썬함수](https://blog.naver.com/PostListByTagName.naver?blogId=infp_joanne&encodedTagName=파이썬함수) (Function) 

 입력값(인자) --> 프로세스(처리) --> 결과값(출력)

 사용 방식 - 함수명(인자) ex. print('Hello World') --> Hello World

[#Type](https://blog.naver.com/PostListByTagName.naver?blogId=infp_joanne&encodedTagName=Type)() : 입력값의 형태를 정의 ex.type(1) = int (정수), type(1.5)=float (실수)

[#파이썬산술연산자](https://blog.naver.com/PostListByTagName.naver?blogId=infp_joanne&encodedTagName=파이썬산술연산자)

  거듭제곱 연산자(`**`)

  거듭제곱의 지수도 정수일 필요가 없음. 루트연산방법 ==>  √2 = 2^(1/2) = 2**(1/2)

  나머지연산자 % ex. 13/5의 나머지=3, 13%5-->3

  몫 연산자 // ex. 13/5의 몫=2, 13//5-->2  

| 연산자기호 | 의미     | 예/결과 |
| ---------- | -------- | ------- |
| +          | 더하기   | 5+2=7   |
| -          | 빼기     | 5-23    |
| *          | 곱하기   | 5*2=10  |
| /          | 나누기   | 5/2=2.5 |
| **         | 거듭제곱 | 5**2=25 |
| %          | 나머지   | 5%2=1   |
| //         | 몫       | 5//2=2  |

[#파이썬](https://blog.naver.com/PostListByTagName.naver?blogId=infp_joanne&encodedTagName=파이썬) 과학적 표현법

(1) 10의 거듭제곱, 10진법 

빛 초당 속동 약 300,000km =300,000,000 ms=3X10^8ms=3*10**8=3e8ms

이 때, 10의 거듭제곱(즉, 10n)의 경우 e로 편리하게 입력. 1,000=1*10^3=1e3

e 다음에는 지수가 양수냐 음수냐에 따라서 양수 기호(+,-)가 들어감 ex. 1e15, 1e-4

단, 1e16이상, 1e-5이상인 경우는 그대로 출력됨.

(2) 2진법, 8진법, 16진법

2진법(0b, binary) - 0,1 ex.17='0b10001'=bin(17)

8진법(0o, 옥타) - 0,1,2,3,4,5,6,7 ex.17='0o21'=oct(17)

16진법(0x, 헥사) - 0,1,2,3,4,5,6,7,8,9,a,b,c,d,e,f ex. 17='ox11'=hex(17)

\* 진법 출력결과는 문자 열이므로, 작은 따옴표(')안에 있음, bin(17)+oct(17) --> 성립안됨. 문자열끼리 연산X

   따라서, 진수 변환은 연산이 모두 끝난 후에 해야함. 

\* 참고 : 111(2)=7=(1*2^2)+(1*2^1)+(1*2^0)

\* 진법을 배우는 이유: 컴퓨터측 입장을 고려하면, 컴퓨터 언어인 진법을 활용하여 학습력과 처리속도를 높임. 

![img](https://postfiles.pstatic.net/MjAyMTA3MTlfNSAg/MDAxNjI2Njc3NTUyODMz.icBsPDdqBCOSVlz89AVFgUGrNPranA9XZSQvy0obMh0g.-e7SMy7UI4Fn1_r62XnFer07YO_4W72DuwteEimV5sgg.JPEG.infp_joanne/0719_02.jpg?type=w773)

[#논리연산](https://blog.naver.com/PostListByTagName.naver?blogId=infp_joanne&encodedTagName=논리연산)

어떤 조건을 만족하는 참(True)와 만족하지 않는 거짓(False)을 이용한 연산 

논리연산(logical operation)=불린연산(boolean operation)

데이터타입은 불(bool) type(True)=bool

'True', 'False'처럼 따옴표를 사용하면 안 됨, why? 문자열로 인식하게 되어 연산이 되지 않음. 

 Ture(O), true, TRUE(X)

False(O), false, FALSE(X)

![img](https://postfiles.pstatic.net/MjAyMTA3MTlfMTQ2/MDAxNjI2NjgwMTA4NTAx.KEaVpycJGLSB0-Et147zbRWG0I1fFumHewJW6txUL4cg.iT-iH9XHDbJ8rE3j0XqD6C35BIZps2xkIOOX3-l2a0Mg.JPEG.infp_joanne/0719_03.jpg?type=w773)

bool 데이터의 경우 논리 연산만 할 수 있음. 

논리곱(and) : A and B, A와 B 모두 참일 때만 참이고 나머지는 거짓

논리합(or): A or B, A,B 중 하나라도 참일 때 참이며, 둘다 거짓일 때 거짓

논리부정(not) : not A, A가 참이면 거짓이고, A가 거짓이면 참.



<진리표>

| A     | B     | A and B | A or B | not A |
| ----- | ----- | ------- | ------ | ----- |
| False | False | False   | False  | True  |
| False | True  | False   | True   | True  |
| True  | False | False   | True   | False |
| True  | True  | True    | True   | False |

[#비교연산](https://blog.naver.com/PostListByTagName.naver?blogId=infp_joanne&encodedTagName=비교연산)

(1) 동등하다 : A=B (X, 대입연산자, 치환, B에 있는 값을 A에 대입한다의 의미),  A==B (O, 비교연산)

(2) 같지않다 : A!=B

\* 우선순위 : 비교 연산자 > 논리 연산자 



깨알팁!

Python/Google Colab에서  Shift+enter 누르믄 실행시킨 후 new command 나옴

괄호와 연산이 함께 있으면 괄호의 우선순위가 높음. 



print(((①3>0)②or(①-5>0))③and((①4>8)②or(①3<0))) --> False

print((③3<0)④and((①-5>0)②and(①1>5))) --> False

