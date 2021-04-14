# P Stage ( 정형데이터 분류 )
#### 학습목표?
- 머신러닝 기본 개념
	- Underfitting & Overfitting
		- What is Underfitting & Overfitting
			- Fit이라는 표현은 데이터를 "잘" 설명할 수 있는 능력
				- Underfitting: 데이터를 설명하지 못함
				- Overfitting: 데이터를 과하게 설명함
		- How to monitoring Underfitting & Overfitting
			- sample dataset을 분석하여 전체 데이터를 잘 표현 하고자 한다.(validation)
		- Regularization
			- Early stopping(정형데이터 사용가능)
			- Parameter norm penalty(정형데이터 사용가능)
			- Data augmentation(정형데이터 사용가능)
			- Noise robustness
			- Label smoothing
			- Dropout(정형데이터 사용가능)
			- Batch normalization
			- SMOTE
	- Validation strategy
		- What is validation strategy
			- Train + Validation + Test
		- Hold-out validation
		- Cross validation
			- Stratified K-Fold
			- Group K-Fold
			- Time series split
	- Reproducibility
		- Fix seed
			- 학습된 모델은 각기 다른 환경에서 초기값이 다른 경우, 다른 결과를 도출할 수 있다. 따라서, 초기값을 고정시켜주어야 한다.
	- Machine learning workflow
#### 학습목표를 달성하기 위해 무엇을 어떻게 했는가?
- Data룰 Time series split 사용으로 성능을 높이려 적용해보았다.
#### 어떤 방식으로 모델을 개선했는가?
- Validation strategy를 time series split으로 성능을 높이려 시도를 하였으나 아직 결과를 도출해내지는 못했다.
#### 오늘 내가 한 행동의 결과로 어떤 지점을 달성하고, 어떠한 깨달음을 얻었는가?
- 아직 데이터 분석을 정확히 하지 못해 어려움이 있다. 우선은 기본 데이터를 통해 모델의 성능을 높이고, 전처리를 진행하려한다.
#### 오늘 나의 학습과 시도가 크게 성공적이지 않아서 아쉬운 것은 무엇인가?
- 데이터에 대한 해석이 명확하지 않은 것이 가장 아쉽다.
#### 내일은 어떻게 다르게 시도해볼 것인가?
- 모델을 바꾼다면 어떻게 결과가 바뀔지 궁금하다.
> 어제와 비교해서, 오늘의 내가 새롭게 시도한 변화는 무엇이고, 어떤 효과가 있었는가?