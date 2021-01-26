# [DAY 3] 파이썬 기초 문법 2
## 1. Python Data Structure
### 강의 소개
- 이번 강의에서는 파이썬에서 많이 사용되는 자료 구조에 대해서 배웁니다.
- 자료구조는 어떤 데이터를 저장할 때, 그 데이터에 특징에 따라 컴퓨터 효율적으로 저리하기 위한 **데이터의 저장 및 표현 방식**을 이야기합니다. 어떤 데이터는 순서가 있다거나, 그 데이터의 나타내는 ID 값과 쌍을 이룬다던가 하는 등의 특징이 나타나게 됩니다. 일반적으로 사용되는 정수, 문자열 등의 변수 타입보다는 **이러한 특징들에 잘 맞는 형태로 데이터를 저장**하게 된다면 훨씬 **효율적으로 컴퓨터의 메모리를 사용**하고, **프로그래머가 코드를 작성하기에도 용이**하게 해줍니다.

#### 특징이 있는 정보는 어떻게 저장하면 좋을까?
> 전화번호부 정보는???<br>
> 은행 번호표 정보는???<br>
> 서정 정보는 ???

### 파이썬 기본 데이터 구조
- 스택과 큐 (stack & queue with list)
- 튜플과 집합 (tuple & set)
- 사전 (dictionary)
- Collection 모듈

#### 스택 (Stack)
- 나중에 넣은 데이터를 먼저 반환하도록 설계된 메모리 구조
- Last In First Out (LIFO)
- Data의 입력을 Push, 출력을 Pop이라고 함.

#### 스택 (stack) with list object
- 리스트를 사용하여 스택 구조를 구현 가능
- push를 메둥(), pop을 pop()를 사용
	- sorted 함수는 정렬된 list를 반환 O, list a 기본 구조 변화 X.
	- sort 함수는 정렬된 list 반환 X, list a 기본 구조 변화 X.
	- pop()은 반환 O, list a 기본 구조 변화 O..
```python
a = [1,2,3,4,5]
a.append(10)
a.append(20)
a.pop() # 20 출력
a.pop() # 10 출력
```
> 20<br>
> 10

#### 큐 (Queue)
- 먼저 넣은 데이터를 먼저 반환하도록 설계된 메모리 구조
- First In First Out (FIFO)
- Stack과 반대되는 개념

#### 큐 (Queue) with list object
- 파이썬은 리스트를 사용하여 큐 구조를 활용
- put를 append(), get을 pop(0)을 사용
``` python
a = [1,2,3,4,5]
a.append(10)
a.append(20)
a.pop(0) # 1 출력
a.pop(0) # 2 출력
```
> 1 <br>
> 2

#### 튜플 (tuple)
- 값의 변경이 불가능한 리스트
- 선언 시 "[]"가 아닌 "()"를 사용
- 리스트의 연산, 인덱싱, 슬라이싱 등을 동일하게 사용

```python
t = (1,2,3)
print(t+t, t*2) # (1,2,3,1,2,3)(1,2,3,1,2,3)
len(t) # 3
t[1] = 5 # error 발생
```
> (1,2,3,1,2,3)(1,2,3,1,2,3)<br>
> 3<br>
> --> error 발생 (변경 불가).

#### Why tuple ???
- 프로그램을 작동하는 동안 변경되지 않은 데이터의 저장<br> ex) 학번, 이름, 우편번호 등등
- 함수의 반환 값 등 사용자의 실수에 의한 에러를 사전에 방지.

```python
t = (1) # 일반정수로 인식
type(t)
t = (1,) # 값이 하나인 Tuple은 반드시 ","를 붙여야 함
type(t)
```
>1<br>
>int<br>
>(1,)<br>
>tuple

#### 집합 (set)
- 값을 순서없이 저장, 중복 불허 하는 자료형
- set 객체 선언을 이용하여 객체 생성

```python
s = set([1,2,3,1,2,3]) # set 함수를 사용 1,2,3 집합 객체 생성, a = {1,2,3,4,5}도 가능
print(s)
s.add(1) # 한 원소 1만 추가, 중복 불허로 추가 되지 않음
print(s)
s.remove(1) # 1 삭제
print(s)
s.update([1,4,5,6,7]) # [1,4,5,6,7] 추가
print(s)
s.discard(3) # 3 삭제
print(s)
s.clear() # 모든 원소 삭제
```
>{1,2,3}<br>
>{1,2,3}<br>
>{2,3}<br>
>{1,2,3,4,5,6,7}<br>
>{1,2,4,5,6,7}

#### 수학에서 활용하는 다양한 집합연산 가능
```python
s1 = set([1,2,3,4,5])
s2 = set([3,4,5,6,7])
sq.union(s2) # s1과 s2의 합집합 {1,2,3,4,5,6,7}
s1 | s2 # {1,2,3,4,5,6,7}
s1.intersection(s2) # s1과 s2의 교집합 {3,4,5}
s1 & s2 # {3,4,5}
s1.difference(s2) # s1과 s2의 차집합 {1,2}
s1 - s2 # {1,2}
```

#### 사전 (dictionary)
- 데이터를 저장 할 때는 구분 지을 수 있는 값을 함께 저장<br> ex) 주민등록 번호, 제품 모델 번호
- 구분을 위한 데이터 고유값을 Identifier 또는 Key 라고함
- Key 값을 활용하여, 데이터 값(Value)을 관리함
- key와 value를 매칭하여 key로 value를 검색
- 다른 언어에서는 Hash Table 이라는 용어를 사용
- {Key1:Value1, Key2:Value2, Key3:Value3 ...} 형태
```python
country_code = {}
country_code = {"America" : 1, "Korea" : 82, "China" : 86, "Japan" : 81}
print(country_code)
print(country_code.items()) # Dict 데이터 출력, type은 tuple
print(country_code.keys()) # Dict 키 값만 출력
country_code["German"] = 49 # Dict 추가
print(country_code)
print(country_code.values()) # Dict Value만 출력
```
>{"America" : 1, "Korea" : 82, "China" : 86, "Japan" : 81}<br>
>dict_items([('America', 1), ('China', 86), ('Korea', 82), ('Japan', 81)])<br>
>dict_keys(["America", "China", "Korea", "Japan"])<br>
>{"America" : 1, "German" : 49. "Korea" : 82, "China" : 86, "Japan" : 81}<br>
>dic_values([1, 49, 86, 82, 81])

```
cmder에서 데이터나 링크로 다운받는 방법
--> wget (URL)
```
#### Collections
- List, Tuple, Dict에 대한 Python Bulit-in 확장 자료 구조(모듈)
- 편의성, 실행 효율 등을 사용자에게 제공함
- 아래의 모듈이 존재함

```python
from collections import deque
from collections import Counter
from collections import OrderedDict
from collections import defaultdict
from collections import namedtuple
```
#### deque
- stack과 queue를 지원하는 모듈
- List에 비해 효율적인 = 빠른 자료 저장 방식을 지원함
- rotate, reverse 등 Linked List의 특성을 지원함
- 기존 list 형태의 함수를 모두 지원함
- deque는 기존 list 보다 효율적인 자료구조를 제공
- 효율적 메모리 구조로 처리 속도 향상

```python
from collections import deque

deque_list = deque()
for i in range(5):
	deque_list.append(i)
print(deque_list) # deque([0,1,2,3,4])
deque_list.appendleft(10)
print(deque_list) # deque([10,0,1,2,3,4])
deque_list.rotate(1)
print(deque_list) # deque([4,10,0,1,2,3])
deque_list.rotate(1)
print(deque_list) # deque([3,4,10,0,1,2])
deque_list.extend([5,6,7])
print(deque_list) # deque([3,4,10,0,1,2,5,6,7])
deque_list.extendleft([5,6,7])
print(deque_list) # deque([5,6,7,3,4,10,0,1,2,5,6,7])
```
```
jupyter notebook에서 함수 시간 재기
%timeit [함수명]
```

#### OrderedDict
- Dict와 달리, 데이터를 입력한 순서대로 dict를 반환함
- 그러나 dict도 python 3.6부터 입력한 순서를 보장하여 출력함

#### defaultdict (익숙하지 않음, 나중에 자세히 공부하고 우선 사용법만)
- Dict type의 값에 기본 값을 지정, 신규값 생성시 사용하는 방법
```python
d = dict()
print(d["first"]) # KeyError:"first" 반환
```
- Dict type의 값에 기본 값을 지정, 신규값 생성시 사용하는 방법
```python
from collections import defaultdict
d = defaultdict(object) # Default dictionary를 생성
d = defaultdict(lambda: 0) # Default 값을 0으로 설점함, 인자는 함수형태로 넣어야하며, 스칼라 값이나 정수로 입력시 error 발생.
print(d["first"])
```
#### Counter
- Sequence type의 data element들의 갯수를 dict 형태로 반환

```python
from collections import Counter

c = Counter() # a new, empty counter
c = Counter('gallahad') # a new counter from an iterable
print(c)
```
> Counter({'a': 3, 'l': 2, 'g': 1, 'd': 1, 'h': 1})

- Set의 연산들을 지원함

#### namedtuple
- Tuple 형태로 Data 구조체를 저장하는 방법
- 저장되는 data의 variable을 사전에 지정해서 저장함

## 2. Pythonic code
### 강의 소개
- 이번 강의에서는 파이썬 특유 문법을 의미하는 **pythonic code**에 대해 배웁니다.
- 파이선의 특징을 가장 잘 살린 파이썬의 문법적 특징을 **pyhonic code**라고 합니다.
- **pythonic code**는 앞서 우리가 살펴보았던 데이터 구조와 달리 특별히 모듈이나 함수가 존재하는 것은 아닙니다. 단지 str이나 다양한 모듈들을 활용하여 **파이썬 특유의 문법**을 표현하는 것입니다. 파이썬 문법의 가장 큰 특징은 **짧고 이해하기 편하다**는 것 입니다. 코드의 수를 줄여서 비록 컴퓨터의 시간은 증가할 수 있지만, 사람의 시간은 아낄 수 있다는 장점이 있습니다.
- **lambda, map, reduce**와 난이도가 있는 파이썬 코딩을 위해 반드시 필요한 **asterisk**의 활용에 대해서 배우도록 하겠습니다.

#### 파이썬 스타일 코드 pythonic code
##### overview
- 파이썬 스타일의 코딩 기법
- 파이썬 특유의 문법을 활용하여 효율적으로 코드를 표현함
- 그러나 더 이상 파이썬 특유는 아님, 많은 언어들이 서로의 장점을 채용
- 고급 코드를 작성 할 수록 더 많이 필요해짐

##### Contents
- split & join
- list comprehension
- enumerate & zip
- lambda & map & reduce
- generator
- asterisk

#### Why Pythonic Code?
- 남 코드에 대한 이해도

	- 많은 개발자들이 python 스타일로 코딩한다.

- 효율
	- 단순 for loop append보다 list가 조금 더 빠르다<br>익숙해지면 코드도 짧아진다.

#### split
- string type의 값을 " 기준값"으로 나눠서 List 형태로 변환.

```python
items = 'zero one two three'.split() # 빈칸을 기준으로 문자열 나누기
print(items)
example = 'python,java,javascript' # ","를 기준으로 문자열 나누기
example.split(",")
print(example)
```
> ['zero', 'one', 'two', 'three']<br>
> ['python', 'java', 'javascript']

#### join
```python
colors = ["red", "blue", "green", "yellow"]
"-".join(colors) # 'red-blue-green-yellow'
colors = ["red", "blue", "green", "yellow"]
"  ".join(colors) # 'red  blue  green  yellow'
```
#### List comprehension
##### Overview
- 기존 List 사용하여 간단히 다른 List를 만드는 기법
- 포관적인 List, 포함되는 리스트라는 의미로 사용됨
- 파이썬에서 가장 많이 사용되는 기법 중 하나
- 일반적으로 for + append 보다 속도가 빠름
```python
result = []
for i in range(10):
	result.append(i)
print(result)
```
> [0,1,2,3,4,5,6,7,8,9]

```python
result = [i for i in range(10)]
print(result)
```
> [0,1,2,3,4,5,6,7,8,9]
```
result = [i for i in range(10) if i % 2 == 0]
print(result)
```
> [0,2,4,6,8]

#### Nested For loop
- 이중 for문과 같다.
- i가 먼저 동작
```python
word_1 = "ii"
word_2 = "cat"
result = [i+j for i in word_1 for j in word_2]
print(result)
```
> ["hc","ha","ht","ic","ia","it"]

> 참고!!<br>
> import pprint는 print 출력을 아래로 출력한다.<br>
> 사용법: pprint.pprint[출력])

- two dimensional : j가 먼저 동작
```python
result = [[i+j for i in word_1] for j in word_2]
print(result)
```
> [["hc","ic"], ["ha","ia"], ["ht", "it"]]

#### Enumerate: list의 element를 추출할 때 번호를 붙여서 추출
```python
for i, v in enumerate(['tic', 'tac', 'toe']):
	print(i,v)
```
> 0, tic<br>
> 1, tac<br>
> 2, toe

#### Zip: 두 개의 list의 값을 병렬적으로 추출함
```python
alist = ['a1', 'a2', 'a3']
blist = ['b1', 'b2', 'b3']
for a, b in zip(alist, blist): # 병렬적으로 값을 추출
	print(a,b)
```
> a1, b1<br>
> a2, b2<br>
> a3, b3<br>

### lambda & map & reduce
#### lambda
- 함수 이름 없이 함수처럼 쓸 수 있는 익명함수
- 수학의 람다 대수에서 유래함

> General function
> ```python
> def f(x,y):
> 	return x+y
> print(f(1, 4))

>Lambda function
>```python
>f = lambda x,y: x+y
>print(f(1,4))

#### lambda problmes: 사용을 권장하지 않으나 많이 사용함.
- 어려운 문법
- 테스트의 어려움
- 문서화 docstring 지원 미비
- 코드 해석의 어려움
- 이름이 존재하지 않는 함수의 출현
- 그래도 많이 쓴다..............

#### map function
- 두 개 이상의 list에도 적용 가능함, if filter도 사용가능
```python
def f(x):
	return x+5
ex = [1,2,3,4,5]
print(list(map(f, ex))
```
> [6,7,8,9,10]

```python
ex = [1,2,3,4,5]
f = lambda x,y : x + y
print(list(map(f, ex, ex))
```
> [2,4,6,8,10]
- python3는 iteration을 생성 -> list를 붙여줘야 map을 사용가능
- 실행시점의 값을 생성, 메모리 효율적

#### reduce function
- map function과 달리 list에 똑같은 함수를 적용해서 통합
``` python
from functools import reduce
print(reduce(lambda x, y: x+y, [1,2,3,4,5]))
```
> 15
#### lambda & map & reduce: Summary
- Lambda, map, reduce는 간단한 코드로 다양한 기능을 제공
- 그러나 코드의 직관성이 떨어져서 lambda나 reduce는 python3에서 사용을 권장하지 않음
- Legacy library나 다양한 머신러닝 코드에서 여전히 사용중

#### Iterable objects
- Sequence형 자료형에서 데이터를 순서대로 추출하는 object
- 내부적 구현으로 __iter__와 __next__가 사용됨
- iter()와 next() 함수로 iterable 객체를 iterator object로 사용.
- `iter(변수)` 변수의 메모리 주소를 가져옴.
- `next(변수)` 변수의 다음 메모리 주소를 가져옴.
	- 다음 주소가 없으면 stop.

#### Generator
- iterable object를 특수한 형태로 사용해주는 함수
- element가 사용되는 시점에 값을 메모리에 반환<br>:yield를 사용해 한번에 하나의 element만 반환함

#### Generator comprehension
- list comprehension과 유사한 형태로 generator형태의 list 생성
- generator expression이라는 이름으로도 부름
- [] 대신 ()를 사용하여 표현.

```python
gen_ex = (n*n for n in range(500))
print(type(gen_ex))
```
> <class 'generator'>

#### When generator
- list 타입의 데이터를 반환해주는 함수는 generator로 만들어라!<br>: 읽기 쉬운 장점, 중간 과정에서 loop가 중단 될 수 있을 때!
- 큰 데이터를 처리할 때는 generator expression을 고려하라!<br> : 데이터가 커도 처리의 어려움이 없음
- 파일 데이터를 처리할 때도 generator를 쓰자.

### function passing arguments
- 함수에 입력되는 arguments의 다양한 형태
	- Keyword arguments
	- Default arguments
	- Variable-length arguments

#### keyword arguments

```python
def abc(a, b):
	return a+b
print(abc(b=1, a=2))
```
#### default arguments

```python
def abc(a, b=2):
	return a+b
print(abc(1)) # b를 변경하고자 한다면, 함수 호출 할 때, 인자값을 같이 넘겨주면 된다.
```
#### variable-length asterisk
- 개수가 정해지지 않은 변수를 함수의 parameter로 사용하는 법
- Keyword arguments와 함께, argument 추가가 가능
- Asterisk(*) 기호를 사용하여 함수의 parameter를 표시함
- 입력된 값은 tuple type으로 사용할 수 있음
- **가변인자는 오직 한 개만 맨 마지막 parameter 위치에 사용가능**
- 가변인자는 일반적으로 `*args`를 변수명으로 사용
- 기존 parameter 이후에 나오는 값을 tuple로 저장함.

```python
def asterisk_test(a, b, *args):
	return a+b+sum(args)
print(asterisk_test(1,2,3,4,5))
```
> 15

#### 키워드 가변인자 (Keyword variable-length)
- Parameter 이름을 따로 지정하지 않고 입력하는 방법
- asterisk(*) 두 개를 사용하여 함수의 parameter를 표시함
- 입력된 값은 dict type으로 사용할 수 있음
- 가변인자는 오직 한 개만 기존 가변인자 다음에 사용
```python
def kwargs_test_1(**kwargs):
	print(kwargs)
kwargs_test_1(first=3, second=4, third=5)
```
> {'first':3, 'second':4, 'third':5}

```python
def kwargs_test_3(one, two=3, *args, **kwargs):
	print(one)
    print(two)
    print(args)
    print(kwargs)
kwargs_test_3(10,30,3,4,5,6,first=3,second=4)
```
> 10<br>
> 30<br>
> (3,4,5,6)<br>
> {'first':3, 'second':4}

- 변수 넣는 순서는 중요하다. (keyword 태를 썼으면 뒤에도 keyword 형태를 써야한다.)

#### asterisk
- 흔히 알고 있는 *를 의미함
- 단순 곱셈, 제곱 연산, 가변 인자 활용 등 다양하게 사용됨
- tuple, dict 등 자료형에 들어가 있는 값을 unpacking
- 함수의 입력값, zip 등에 유용하게 사용가능

```python
def asterisk_test(a, *args):
	print(a, *args)
    print(a, args)
    print(type(args))
    
test = (2,3,4,5,6)
asterisk_test(1, *test)
```
> 1 2 3 4 5 6<br>
> 1 (2,3,4,5,6)<br>
> <class 'tuple'>

```python
print(*["1","2","3","4"])
```
> 1 2 3 4
