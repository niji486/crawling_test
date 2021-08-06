# 데이터 분석을 위한 패키지, NumPy

> NumPy는 파이썬으로 과학 연산을 쉽고 빠르게 할 수 있는 패키지로, 
>
> 다차원 배열 데이터를 효과적으로 처리 (http://www.numpy.org)



(1) 배열 생성하기  : import numpy 

- NumPy 패키지 불러오기 : 패키지 다운로드 필요. 단, 아나콘다 설치한 경우 이미 완료됨.
- import numpy  as np 

(2) NumPy 배열 생성 : np.array

- 시퀀스 데이터(seq_data)를 인자로 받아 NumPy 의 배열 객체(array object) 를 생성 
- 리스트와 튜플 타입의 데이터를 모두 사용할 수 있지만 주로 리스트 데이터를 이용 
- 리스트로부터 NumPy의 1차원 배열을 생성, 인자로 정수와 실수가 혼합된 경우, 실수로 변환
- np.array()에 리스트 데이터를 직접 넣어서 배열 객체를 생성 가능 

```python
# NumPy 패키지 불러오기 
import numpy as np

# 배열 생성
 data1 = [0,1,2,3,4,5]
 a1 = np.array(data1)
 a1
▷ array([0, 1, 2, 3, 4, 5])
# 배열 생성 (혼합시, 실수로 모두 변환)
data2 = [0.1,5,4,12,0.5]
a2 = np.array(data2)
a2
▷ array([ 0.1,  5. ,  4. , 12. ,  0.5])

# 타입 고려시, a1은 정수로된 64비트, a2는 실수로 된 64비트
[4]
a1.dtype
▷ dtype('int64')
[5]
a2.dtype
▷ dtype('float64')

# array()에 직접 리스트 입력 가능 
np.array([0.5,2,0.01,8])
▷ array([0.5 , 2.  , 0.01, 8.  ])

np.array([[1,2,3],[4,5,6],[7,8,9]])
▷ array([[1, 2, 3],
       [4, 5, 6],
       [7, 8, 9]])
```

(3) 범위와 간격을 지

정해 배열 생성 : np.arange 

- arr_obj = np.arange([start], [stop], [step])
- start부터 시작해 stop전까지 step의 간격으로 NumPy의 배열을 생성 
- step 이 1 인 경우 생략가능, start가 0인 경우도 생략가능 
- np.arange(stop) : start 0 이고, step 1인 경우

```python
# (start, stop, step)
np.arange(0,10,2)
▷ array([0, 2, 4, 6, 8])
# (start, stop)
np.arange(1,10)
▷ array([1, 2, 3, 4, 5, 6, 7, 8, 9])
# (stop)
np.arange(5)
▷ array([0, 1, 2, 3, 4])
```



(4) 행렬로 생성 : np.arrange(x*y), reshape(x,y)

- arrange로 숫자를 생성한 후, reshape으로 4 * 3 행렬로 만들어줌 
- 배열의 형태를 알기 위해서는 .shape 실행 

```python
# arange로는 1단 배열 
np.arange(12)
▷ array([ 0,  1,  2,  3,  4,  5,  6,  7,  8,  9, 10, 11])

# arange().reshape()으로 다차원 행렬로 생성
np.arange(12).reshape(4,3)
▷ array([[ 0,  1,  2],
       [ 3,  4,  5],
       [ 6,  7,  8],
       [ 9, 10, 11]])

# 배열의 형태를 알기위한 .shape
b1 = np.arange(12).reshape(4,3)
b1.shape
▷ (4, 3)

# 1단인 경우, 값은 Null 을 산출
b2 = np.arange(5)
b2.shape
▷ (5,)
```



(5)  범위와 데이터 갯수를 지정해 배열 생성 : np.linspace

- arr_obj=np.linspace(start, stop, num)
- start부터 시작해 stop 까지 num 개의 NumPy 배열을 생성 
- num을 지정하지 않으면 50으로 간주 

```python
# linspace()
np.linspace(1,10,10)
▷ array([ 1.,  2.,  3.,  4.,  5.,  6.,  7.,  8.,  9., 10.])

# linspace stop에 np.pi(파이, 3.14) 적용
np.linspace(0, np.pi, 20)
▷ array([0.        , 0.16534698, 0.33069396, 0.49604095, 0.66138793,
       0.82673491, 0.99208189, 1.15742887, 1.32277585, 1.48812284,
       1.65346982, 1.8188168 , 1.98416378, 2.14951076, 2.31485774,
       2.48020473, 2.64555171, 2.81089869, 2.97624567, 3.14159265])

# num지정하지 않는 경우, 50개까지.
np.linspace(0,100)
▷ array([  0.        ,   2.04081633,   4.08163265,   6.12244898,
         8.16326531,  10.20408163,  12.24489796,  14.28571429,
        16.32653061,  18.36734694,  20.40816327,  22.44897959,
        24.48979592,  26.53061224,  28.57142857,  30.6122449 ,
        32.65306122,  34.69387755,  36.73469388,  38.7755102 ,
        40.81632653,  42.85714286,  44.89795918,  46.93877551,
        48.97959184,  51.02040816,  53.06122449,  55.10204082,
        57.14285714,  59.18367347,  61.2244898 ,  63.26530612,
        65.30612245,  67.34693878,  69.3877551 ,  71.42857143,
        73.46938776,  75.51020408,  77.55102041,  79.59183673,
        81.63265306,  83.67346939,  85.71428571,  87.75510204,
        89.79591837,  91.83673469,  93.87755102,  95.91836735,
        97.95918367, 100.        ])
```



(6) 모든 원소가 0 혹은 1인 다차원 배열 : zeors(), ones()

- arr_zero_n=np.zeros(n) : n개의 원소가 모두 0을 갖는 1차원 배열
- arr_zero_mxn=np.zeros((m,n)) : 모든 원소가 모두 0을 갖는 m * n 형태의 배열(행렬)
- arr_one_n=np.one(n) : n개의 원소가 모두 1을 갖는 1차원 배열
- arr_one_mxn=np.one((m,n)) : 모든 원소가 모두 1을 갖는 m * n 형태의 배열(행렬)

```python
np.zeros(10)
▷ array([0., 0., 0., 0., 0., 0., 0., 0., 0., 0.])

np.zeros((3,4))
▷ array([[0., 0., 0., 0.],
       [0., 0., 0., 0.],
       [0., 0., 0., 0.]])
       
np.ones(5)
▷ array([1., 1., 1., 1., 1.])

np.ones((3,5))
▷ array([[1., 1., 1., 1., 1.],
       [1., 1., 1., 1., 1.],
       [1., 1., 1., 1., 1.]])
       
```



(7) 단위행렬(Identity matrix)로 생성하는 방법 : np.eye(n)

- 단위행렬 : n * n 인 정사각형에서 주 대각선이 모두 1이고, 나머지는 0인 행렬을 의미 
- arr_I=np.eye(n) : n*n 의 단위행렬을 생성 

```python
np.eye(3)
▷ array([[1., 0., 0.],
       [0., 1., 0.],
       [0., 0., 1.]])
```
