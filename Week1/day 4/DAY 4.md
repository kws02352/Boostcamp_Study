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











