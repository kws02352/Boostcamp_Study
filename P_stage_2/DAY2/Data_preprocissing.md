# P Stage ( 정형데이터 분류 )
#### 학습목표?
- 데이터 전처리
	- 머신러닝 모델에 데이터를 입력하기 위해 데이터를 처리하는 과정<br>
	-> EDA에 따라 달라지는 데이터 전처리<br>
    -> 모델, 목적에 따라 달라지는 데이터 전처리<br>
    선형 모델? 트리? 딥러닝? -> 달라지는 데이터 전처리 방식
    
	- 연속형, 범주형 처리
		- continuous type
			- Scaling
				- 데이터의 단위 혹은 분포를 변경
					- 선형기반의 모델(선형회귀, 딥러닝 등)인 경우 변수들 간의 스케일을 맞추는 것이 필수적
				1. Scale
					- Min Max scaling
					- Standard Scaling
					- Robust Scaling: 보통 이상치의 영향을 덜 받는다.
				2. Scale + Distribution<br>
					- Log transformation
					- Quantile transformation: 어떠한 데이터가 들어와도 정규분포에 맞출 수 있다.<br>
				3. +Binning 
					- 넓고 얇은 다봉분포
					- Overfitting 방지
		- categorical type
			- Encoding
				1. One hot encoding
				2. Label encoding: 고유 label 번호
				3. Frequency encoding: 빈도수
				4. Target encoding
				5. Embedding: Word2Vec
	- 결측치 처리
		- pattern
			- Missing data patterns
		- univariate
			- 제거
			- 평균값 삽입
			- 중위값 삽입
			- 상수값 삽입
		- multivariate
	- 이상치 처리
		- 이상치란
			- 일반적으로 데이터 중에서 다른 데이터들과 크게 다른 것
		- 이상치 탐색
			- Z-Score
			- IQR
		- 이상치 처리 관점
			- 정성적인 측면
				- 이상치 발생 이유
				- 이상치의 의미
			- 성능적인 측면
				- Train Test Distribution

#### 학습목표를 달성하기 위해 무엇을 어떻게 했는가?
- PCA를 활용하여 데이터의 차원을 축소한 vector의 형태로 데이터를 보았다.
#### 어떤 방식으로 모델을 개선했는가?
- 모델은 아직 건드리지 않았으나, XGboost, LightGBM, CATBoost에 대해서 알아보았다.
#### 오늘 내가 한 행동의 결과로 어떤 지점을 달성하고, 어떠한 깨달음을 얻었는가?
- 아직 데이터의 분석을 하고 있으나, 점점 데이터에 대해서 알아가지만 활용 방법에 대해서 더 많은 공부가 필요하다.
#### 오늘 나의 학습과 시도가 크게 성공적이지 않아서 아쉬운 것은 무엇인가?
- 데이터에 대한 해석이 명확하지 않아 모델을 건드리지 못 하는 점이 가장 아쉽다.
#### 내일은 어떻게 다르게 시도해볼 것인가?
- 데이터 분석을 수요일까지 마무리 짓고 목요일에는 모델에 시간을 쓸 생각이다.
> 어제와 비교해서, 오늘의 내가 새롭게 시도한 변화는 무엇이고, 어떤 효과가 있었는가?
