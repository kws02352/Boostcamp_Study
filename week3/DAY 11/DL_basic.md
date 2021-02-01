# [DLBasic] 딥러닝 기본 용어 설명 - Historical Review

#### Key Components of Deep Learning
> 딥러닝의 키포인트!! 논문을 본다고 했을 때, 어떠한 관점으로 봐야 하는가
- Data
	- data depend on the type of the problem to solve.
	- detection, classification, segmentation, etc,,,
- Model
- Loss function
	- The loss function is a proxy of what we want to achieve.
	- Regression task(MSE), Classification task(cross entropy), Probabilistic Task(MLE), etc...
- algorithm
	- Optimization Algorithm
	- SGD, Momentum, Adam, etc...
	- Dropout, Early stopping, Weight decay, etc...

## Historical Review
#### 2012 - AlexNet
- Classification
- input: 224 x 224

#### 2013 - DQN
- Reinforcement Learning
- based on Q-learning algorithm.

#### 2014 - Encoder / Decoder
- Neural Machine Translation(NMT)
- sequence to sequence

#### 2014 - Adam Optimizer
#### 2015 - Generative Adversarial Network
- Ian Goodfellow 저자
- Generator / Discriminator

#### 2015 - Residual Networks
#### 2017 - Transformer
- Attention Is All You Need

#### 2018 - Bert(fine-tuned NLP models)
- Bidirectional Encoder Representations from Transformers
#### 2019 - Big Language Models(GPT-X)
#### 2020 - Self-Supervised Learning

# [DLBasic] PyTorch 시작하기
#### Tensorflow
- define and run 구조

#### PyTorch
- Numpy + AutoGrad(자동 미분) + Function
- Numpy 구조를 가지는 Tensor 객체로 array 표현
- 자동미분을 지원하여 DL 연산을 지원
- 다양한 형태의 DL을 지원하는 함수와 모델을 지원함
---
#### 알아야 할 점!!!
- torch는 numpy와 연산이 비슷하다.
- 처음보는 torch함수는 code level로 항상 들어가자!


































