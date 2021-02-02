# [DLBasic] 뉴럴 네트워크 - MLP
#### Linear Neural Networks
![linear_NN](./image/6.JPG)<br>
- 편미분을 이용하여 update.
- stepsize가 중요
- 물론 다차원의 input과 output을 다룬다.

#### Beyond Linear Neural Network
- Activation functions

![Activation_function](./image/7.JPG)<br>
#### Multi-layer perceptron
- Loss

![Loss](./image/8.JPG)<br>

### Dataset 다루기
- Dataset 구성

```python
주로 (torch.utils.data.Dataset)으로 호출
def __init__, # 초기값
def __len__, # 데이터의 전체 길이
def __getitem__ # index 값으로 데이터 호출
```
- `DataLoader # 데이터 가지고 오기`

## 공부한 부분
- Neural Network의 전반적인 내용에 대해 학습
- 이번 강의에서는 실습 위주이기 때문에 개인적으로 코드를 보며 공부를 진행