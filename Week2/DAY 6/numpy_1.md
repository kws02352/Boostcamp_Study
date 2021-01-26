# [AI Math 0강] numpy

## 강의 소개
- numpy는 파이선으로 진행되는 모든 데이터 분석과 인공지능 학습에 있어 가장 필수적으로 이해해야 하는 도구 이다.
- numpy는 numerical python의 약자로 일반적으로 과학계산에서 많이 사용하는 선형대수의 계산식을 파이썬으로 구현할 수 있도록 도와주는 라이브러리이다. 기존 가장 대중적으로 쓰이는 도구는 MATLAB인데 MATLAB의 역할을 파이썬의 도구로 생각하면 좋다.
- numpy는 numpy 자체로도 많이 사용되지만 이후에 사용되는 SciPy나 Pandas의 base 객체로도 사용되며, numpy에서 사용되는 다양한 코드 표현법을 그대로 pythorch와 tensorflow에 사용하는 경우가 많아 numpy의 활용법은 반드시 알아 둘 필요가 있다.
---
### Numerical Python - numpy
`conda install numpy`
- 어떻게 행렬과 매트릭스를 코드로 표현할 것인가?

#### Numpy의 특징
- 일반 List에 비해 빠르고, 메모리 효율적
- 반복문 없이 데이터 배열에 대한 처리를 지원함
- 선형대수와 관련된 다양한 기능을 제공함
- C, C++, 포트란 등의 언어와 통합 가능

#### ndarray (numpy dimension array)
> array creation
> ```pyrhon
> test_array = np.array([1, 4, 5, 8], float) # np.array: 배열을 생성, float: 하나의 데이터 타입만 배열에 넣을 수 있음.
> print(test_array) # nparray
> type(test_array[3]) # float 으로 적혀있다.
> print(test_array.shape) # Array(배열)의 shape을 반환함
> print(test_array.dtype) # Array(배열) 전체의 데이터 Type을 반환함
> ```
- List와 가장 큰 차이점 -> dynamic typing not supported
> list는 [0, 1.2, "가나"]
- C의 Array를 사용하여 배열을 생성함

#### numpy vs list

||numpy|python|
|---|---|---|
|저장 방법|데이터가 차례대로 들어감.|데이터의 주소 값이 들어감.|
|장점|연산이 상당히 쉽다.|List의 변형이 상당히 쉽다.|

#### Rank --> ndim(number of dimensions)
|Rank|Name|Example|
|---|---|---|
|0|scalar|7|
|1|vector|[10, 10]|
|2|matrix|[[10, 10], [15, 15]]|
|3|3-tensor|[[[1,5,9],[2,6,10]],[[3,7,11],[4,8,12]]|
|n|n-tensor||
