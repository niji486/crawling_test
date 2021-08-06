# 데이터 분석을 위한 패키지, NumPy(2)

> NumPy는 파이썬으로 과학 연산을 쉽고 빠르게 할 수 있는 패키지로, 
>
> 다차원 배열 데이터를 효과적으로 처리 (http://www.numpy.org)

(8) 데이터 타입의 배열로 변환 : astype ()

- 정수(int), 실수(float), 문자열(str)로 각각 변환
- num_arr = str_arr.astype(dtype)

```python
# numpy 호출 as np 후, 직접 문자열로 된 배열 생성  dtype='<U8'
import numpy as np
np.array(['1.5','0.62','2','3.14','3.141592'])
▷ array(['1.5', '0.62', '2', '3.14', '3.141592'], dtype='<U8')
#dtype='<U8'의 의미는 유니코드의 문자열이며 소수점 이후 최대길이 8

#astype : 문자열 --> 실수로 변환 
str_a1=np.array(['1.567','0.123','5.123','9','8'])
num_a1=str_a1.astype(float)
num_a1
▷ array([1.567, 0.123, 5.123, 9.   , 8.   ])
# dtype을 통해 문자열이 실수로 변환되었음을 확인
str_a1.dtype
▷ dtype('<U5') #유니코드 문자열 소수점 이후 최대 길이 5
num_a1.dtype
▷ dtype('float64') #실수 64비트

#astype : 문자열 --> 정수로 변환 
str_a2 = np.array(['1','3','5','7','9'])
num_a2 = str_a2.astype(int)
num_a2
▷ array([1, 3, 5, 7, 9])
# dtype을 통해 문자열이 실수로 변환되었음을 확인
str_a2.dtype
▷ dtype('<U1') #유니코드 문자열 정수(소수점 이하 자리 없음)
num_a2.dtype
▷ dtype('int64') #정수 64비트
```



(9) 난수(random number) 배열의 생성 : random.rand ()

- random 모듈을 이용해 임의의 숫자인 난수를 생성 
- rand() -> 실수, randint()->정수
- rand_num=np.random.rand([d0,d1,...,dn]) --> 배열의 형태를 지정하는 것
  ex) np.random.rand(d1,d2) : d2 개의 인자를 가진 d1 개의 리스트, 늘어날수록 d1 * d2
- rand_num=np.random.randint([low], high [.size]) --> low, high 사이의 정수 중의 난수

```python
# 실수, 3개 인자를 가진 2개 리스트 구성의 행렬 (총 6개 원소)
np.random.rand(2,3)
▷ array([[0.73317237, 0.70288271, 0.40642295],
       [0.4391713 , 0.04766558, 0.07015463]])

# 실수, (총 1개 원소)
np.random.rand()
▷ 0.5600648376118497

# 실수, (총 2*3*4=24개 원소)
np.random.rand(2,3,4)
▷ array([[[0.79549992, 0.58864088, 0.15399349, 0.54081634],
        [0.00438089, 0.47917658, 0.67850666, 0.57360715],
        [0.89840467, 0.18897801, 0.13754057, 0.01858663]],

       [[0.60272646, 0.51502268, 0.37675932, 0.1711558 ],
        [0.02088301, 0.26417719, 0.32666339, 0.88784962],
        [0.94121458, 0.23067758, 0.60432213, 0.42016662]]])

# 정수, low=0(생략), high=10-1, size=3*4, 12개 
np.random.randint(10,size=(3,4))
▷ array([[0, 1, 1, 5],
       [9, 7, 1, 3],
       [9, 2, 7, 2]])

# 정수, low=1, high=30-1, size=1(생략)
np.random.randint(1,30)
▷ 12
```

(10) 배열의 연산 

- Numpy 배열에서도 다양하게 연산 가능. 단, 배열의 형태(shape)이 같아야  +,-, *, / 가능 
- 배열의 형태가 같다는 건, ndarray.shape이 같다는 의미 
- 1차원의 배열은 두 배열의 원소 개수가 같아야 하고, 2차원 배열은 m * n 의 m, n 이 동일해야 함.  

```python
# 같은 형태(shape, 정수, 4개 원소)의 행렬 2개 생성
arr1 = np.array([10,20,30,40])
arr2 = np.array([1,2,3,4])

# 같은 위치끼리 더하기
arr1 + arr2
▷ array([11, 22, 33, 44])

# 같은 위치끼리 빼기
arr1 - arr2
▷ array([ 9, 18, 27, 36])

# 2 곱하기
arr2 * 2
▷ array([2, 4, 6, 8])

# 제곱
arr2 **2
▷ array([ 1,  4,  9, 16])

# 같은 위치끼리 곱하기
arr1 * arr2
▷ array([ 10,  40,  90, 160])

# 수식대로 연산
arr1 / (arr2 **2)
▷ array([10.        ,  5.        ,  3.33333333,  2.5       ])

# 크기비교
arr1 > 20
▷ array([False, False,  True,  True])
```

(11) 통계를 위한 연산 :  sum(), mean(), std(), var(),min(), max(), cumsum(), cumprod()

- 배열의 합, 평균, 표준편차, 분산, 최소값/최대값, 누적 합/곱의 많이 사용하는 Method 有

```python
# 배열 생성
arr3 = np.arange(5)
arr3
▷ array([0, 1, 2, 3, 4])

# 합, 평균, 표준편차, 분산
[arr3.sum(), arr3.mean(), arr3.std(), arr3.var()]
▷ [10, 2.0, 1.4142135623730951, 2.0]

# 최소값, 최대값
[arr3.min(), arr3.max()]
▷ [0, 4]

# 배열 생성
arr4 = np.arange(1,5)
arr4
▷ array([1, 2, 3, 4])

# 누적합, 누적곱, np.array.shape으로 출력
[arr4.cumsum(), arr4.cumprod()]
▷ [array([ 1,  3,  6, 10]), array([ 1,  2,  6, 24])]
```

(12) 행렬 연산 : dot()m transpose(), linalg.det()

- 선형대수(Linear algebra)를 위한 행렬(2차원 배열) 연산도 지원 
- 행렬간 곱(dot), 전치 행렬 구하기(transpose), 역 행렬 구하기(linalg.det)

```python
# 2차원 배열 생성
A = np.array([0,1,2,3]).reshape(2,2)
A
▷ array([[0, 1],
       [2, 3]])

B = np.array([3,2,0,1]).reshape(2,2)
B
▷ array([[3, 2],
       [0, 1]])
#행렬간 곱 
A.dot(B)
▷ array([[0, 1],

np.dot(A,B)
▷ array([[0, 1],
       [6, 7]])
       
#A행렬의 전치 행렬 구하기
np.transpose(A)
▷ array([[0, 2],
       [1, 3]])

A.transpose()
▷ array([[0, 2],
       [1, 3]])

# 역행렬 구하기
np.linalg.inv(A)
array([[-1.5,  0.5],
       [ 1. ,  0. ]])
       
# 이건 뭔지...
np.linalg.det(A)
-2.0
```

(12) 배열의 인덱싱 : 

- 배열의 위치, 조건, 범위를 지정해 배열에서 필요한 원소를 선택. 선택된 원소는 값을 가져오거나 변경.
- 배열의 위치, 조건을 지정해 원소를 선택하는 건 인덱싱(indexing)
- 배열의 범위를 지정해 원소를 선택하는 건 슬라이싱(slicing)
- 형식 : 배열명[위치]

```python
#배열 생성
a1 = np.array([0,10,20,30,40,50])
a1
▷ array([ 0, 10, 20, 30, 40, 50])
# 첫번째 원소(0) 출력
a1[0]
▷ 0
# 다섯번쨰 원소(4+1) 출력
a1[4]
▷ 40
# 여섯번째 원소(5+1)을 70으로 변경
a1[5] = 70
a1
▷ array([ 0, 10, 20, 30, 40, 70])
# 두번째, 네번째, 다섯번쨰 원소 순서대로 출력
a1[[1,3,4]]
▷ array([10, 30, 40])

# 배열 생성, 10~99, 10단위로 3 * 3 배열
a2 = np.arange(10,100,10).reshape(3,3)
a2
▷ array([[10, 20, 30],
       [40, 50, 60],
       [70, 80, 90]])
# 첫번째(0+1)행의 세번째(2+1) 호출
a2[0,2]
▷ 30
# 세번째(2+1)행의 세번째(2+1)을 95로 변경하여 호출
a2[2,2] = 95
a2
▷ array([[10, 20, 30],
       [40, 50, 60],
       [70, 80, 95]])
# 두번째(1+1)행 호출
a2[1]
▷ array([40, 50, 60])
# 두번째(1+1)행 변경
a2[1] = [47,57,67]
a2
▷ array([[10, 20, 30],
       [47, 57, 67],
       [70, 80, 95]])
# (0,0), (2,1) 좌표의 값 호출
a2[[0,2],[0,1]]
▷ array([10, 80])

# 배열 생성 후, 3이상의 값만 호출
a = np.array([1,2,3,4,5,6])
a[a > 3]
▷ array([4, 5, 6])
# 2로 나눈 후 나머지가 0인 것 호출 
a[(a % 2 == 0)]
▷ array([2, 4, 6])
```



(13) 배열의 슬라이싱 

- 범위를 지정해 배열의 일부분을 선택하는 슬라이싱 
- 1차원 배열 기준 : 배열[시작`_`위치:끝`_`위치] --> 시작`_`위치~끝`_`위치-1
  시작을 지정하기 않으면 --> 시작`_`위치~끝`_`위치-1
  끝을 지정하지 않으면 --> 시작`_`위치~배열의 끝

```python
# 배열생성 후 두번째(1+1)에서 네번째(순서는 4-1=3)까지 호출
b1 = np.array([0,10,20,30,40,50])
b1[1:4]
▷ array([10, 20, 30])
# 첫번째(0+1)에서 세번째(순서는 3-1=2)까지 호출
b1[:3]
▷ array([ 0, 10, 20])
# 세번째(2+1)에서 배열 끝까지 호출
b1[2:]
▷ array([20, 30, 40, 50])
# 세번째(2+1)에서 다섯번째(순서는 5-1=4)까지 숫자 값 변경
b1[2:5] =np.array([25,35,45])
b1
array([ 0, 10, 25, 35, 45, 50])
# 네번째(3+1)에서 여섯번째(순서는 6-1=5)까지 숫자값 변경 
b1[3:6] = 60
b1
▷ array([ 0, 10, 25, 60, 60, 60])

#3*3차원 행렬 생성
b2 = np.arange(10,100,10).reshape(3,3)
b2
▷ array([[10, 20, 30],
       [40, 50, 60],
       [70, 80, 90]])
# 0~2 행 * 1~2 원소
b2[:3, 1:]
▷ array([[20, 30],
       [50, 60],
       [80, 90]])
# 1행, 0~1 원소
b2[1][0:2]
▷ array([40, 50])
# 0~2 행, 1~2 원소를 값 변경
b2[0:2, 1:3] = np.array([[25,35], [55,65]])
b2
array([[10, 25, 35],
       [40, 55, 65],
       [70, 80, 90]])
```
