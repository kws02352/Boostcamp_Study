# [DAY 4] 파이썬 기초 문법 3
## Python Object Oriented Programming
### 강의 소개
- 이번 강의에서는 객체지향 프로그래밍 언어, Object Oriented Programming(OOP)에 대해서 배웁니다.
- OOP는 프로그래밍 언어를 배우는 데 있어서 매우 중요한 개념입니다. 파이썬 자체도 OOP 형태로 구성되어 있기도 하지만, 파이썬 나오기 전에 대세 언어들이었던 자바, C++, C# 같은 언어들이 모두 OOP 기반의 언어들입니다. OOP를 배우는 것은 이전에 우리가 if 문이나 loop 문을 배우듯이 프로그래밍 언어를 배우는 데 있어 가장 기본적인 개념이 되었습니다.
- 고난이도 프로그래밍을 위한 길로 생각하고 이번 챕터를 공부해보시기 바랍니다.

#### 파이썬을 개발하는 방법
- 만들어 놓은 코드를 재사용하고 싶다!
#### 클래스와 객체 
- 객체 지향 언어의 이해 

#### 객체지향 프로그래밍 개요
- Object-Oriented Programming, OOP
- 객체: 실생활에서 일종의 물건 속성(Attribute)와 행동(Action)을 가짐
- OOP는 이러한 객체 개념을 프로그램으로 표현 속성은 변수(variable), 행동은 함수(method)로 표현됨
- 파이썬 역시 객체 지향 프로그램 언어

### Objects in Python
#### Class 선언하기
- class 선언, object는 python3에서 자동 상속

```python
class SoccerPlayer(object):
```
- class: class 예약어
- SoccerPlayer: class 이름
- object: 상속받는 객체명

> [알아두면 상식] Python naming rule<br>
> 변수와 class명 함수명은 짓는 방식이 존재<br>
> - snake_case: 띄어쓰기 부분에 "_"를 추가<br>
뱀 처럼 늘여쓰기, 파이썬 함수/변수명에 사용
> - CamelCase:  띄어쓰기 부분에 대문자<br>
> 낙타의 등 모양, 파이썬 Class명에 사용

#### Attribute 추가하기
- Attribute 추가는 __init__, self와 함께!<br>
__init__은 객체 초기화 예약 함수
```python
class SoccerPlayer(object):
	def __init__(sel, name, position, back_number):
    	self.name = name
        self.position = position
        self.back_number = back_number
```
> [알아두면 상식] 파이썬에서 __의미
> - __는 특수한 예약 함수나 변수 그리고 함수명 변경(맨글링)으로 사용<br>
예) `__main__, __add__, __str__, __eq__ `

#### method 구현하기
- method(Action) 추가는 기존 함수와 같으나, 반드시 `self`를 추가해야만 class 함수로 인정됨

#### objects(instance) 사용하기
- Object 이름 선언과 함께 초기값 입력 하기

`jinhyun = SoccerPlayer("Jinhyun", "MF", 10)`
> Jinhyun: 객체명<br>
> SoccerPlayer: class명<br>
> ("Jinhyun", "MF", 10): __init__ 함수 Interface, 초기값

#### OOP characteristics
> Inheritance(상속), Polymorphism(다형성), Visibility
#### Inheritance(상속)
- 부모 클래스로부터 속성과 Method를 물려받은 자식 클래스를 생성 하는 것.
- `super().`: 부모 객체를 사용하는 것.

#### Polymorphism(다형성)
- 같은 이름 메소드의 내부 로직을 다르게 작성
- Dynamic Typing 특성으로 인해 파이썬에서는 같은 부모 클래스의 상속에서 주로 발생함
- 중요한 OOP의 개념 그러나 너무 깊이 알 필요 X

#### Visibility(가시성)
- 객체의 정보를 볼 수 있는 레벨을 조절하는 것
- 누구나 객체 안에 모든 변수를 볼 필요가 없음
> 1) 객체를 사용하는 사용자가 임의로 정보 수정
> 2) 필요 없는 정보에는 접근 할 필요가 없음
> 3) 만약 제품으로 판매한다면? 소스의 보호

> [알아두면 상식] Encapsulation<br>
> - 캡슐화 또는 정보 은닉(Information Hiding)
> - Class를 설계할 때, 클래스 간 간섭/정보공유의 최소화
> - 심판 클래스가 축구 선수 클래스 가족 정보를 알아야 하나?
> - 캡슐을 던지듯, 인터페이스만 알아서 써야함.

> `__items`에서 앞에 "__"는 private 변수로 선언하는 것. 즉, 타객체가 접근 못함.

### decorate
> `@property`
- first-class objects(일급 객체) : 파이썬의 함수는 일급함수!!!
	- 일등 함수 또는 일급 객체
	- 변수나 데이터 구조에 할당이 가능한 객체
	- 파라메터로 전달이 가능 + 리턴 값으로 사용
```python
def square(x):
	return x * x
f = square # 함수를 변수로 사용, 메모리 주소.
f(5)
```
- Inner function
	- 함수 내에 또 다른 함수가 존재
```python
def print_msg(msg):
	def printer():
    	print(msg)
    printer()
print_msg("Hello, Python")
```
- closures: inner function을 return 값으로 반환
```python
def print_msg(msg):
	def printer():
    	print(msg)
    return printer
    
another = print_msg("Hello, Python")
another()
```
## Module and Project
### 강의 소개
- 이번 강의에서는 파이썬 프로젝트의 기본이 되는 모듈과 패키지, 그리고 프로젝트의 개념에 대해서 배웁니다.
- 우리는 앞서 파이썬에서 제공하는 여러가지 모듈들을 사용했습니다. 이러한 모듈과 패키지를 구성하고, 실제로 다른 개발자가 만든 모듈을 사용하는 방법까지 이 챕터에서 다루게 됩니다.
#### Module
- 어떤 대상의 부분 혹은 조각<br>
예) 레고 블록, 벽돌, 자동차 부품들
- 프로그램에서는 작은 프로그램 조각들,<br> 모듈들을 모아서 하나의 큰 프로그램을 개발함
- 프로그램을 모듈화 시키면 다른 프로그램이 사용하기 쉬움<br> 예) 카카오톡 게임을 위한 카카오톡 접속 모듈
#### Package
- 모듈을 모아놓은 단위, 하나의 프로그램
### Module
#### Module 만들기
- 파이썬의 Module == py 파일을 의미
- 같은 폴더에 Module에 해당하는 .py 파일과 사용하는 .py을 저장한 후
- import 문을 사용해서 module을 호출
> #### namespace
> - 몸듈을 호출할 때 범위 정하는 방법
> - 모듈 안에는 함수와 클래스 등이 존재 가능
> - 필요한 내용만 골라서 호출 할 수 있음
> - from과 import 키워드를 사용함
> > Alias 설정하기- 모듈명을 변칭으로 써서 호출하기 <br>
> > `import tensorflow as tf`<br>
> > 모듈에서 특정 함수 또는 클래스만 호출하기<br>
> > `from abc import a`<br>
> > 모듈에서 모든 함수 또는 클래스를 호출하기<br>
> > `from abc import *`
### Package
- 하나의 대형 프로젝트를 만드는 코드의 묶음
- 다양한 모듈들의 합, 폴더로 연결됨
- __init__, __main__등 키워드 파일명이 사용됨
- 다양한 오픈 소스들이 모두 패키지로 관리됨
> from [.현재 디렉토리 기준][..부모 디렉토리 기준] import [절대참조]
