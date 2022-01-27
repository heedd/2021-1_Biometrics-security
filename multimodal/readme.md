# 멀티모달 인식 (multimodal recognition)
## **멀티모달 러닝(multimodal learning)**
* 인간이 오감으로 자극을 인지하는 것과 같이 서로 다른 차원의 데이터의 특징을 추출하고 학습하는 방법
* 해당 과제에서는 얼굴과 홍채 데이터로 인물을 인식하는 네트워크 구현이 목적

## **과제 설명**
  [(1) 모델 1개](https://github.com/heedd/2021-1_Biometrics-security/tree/master/multimodal/%EB%AA%A8%EB%8D%B8%201%EA%B0%9C) 
    : 얼굴과 홍채를 각각 인식하는 각각의 모델 구현 (총 1개의 모델)  
  [(2) 모델 2개](https://github.com/heedd/2021-1_Biometrics-security/tree/master/multimodal/%EB%AA%A8%EB%8D%B8%202%EA%B0%9C) 
    : 얼굴과 홍채를 각각 인식하는 각각의 모델 구현 (총 2개의 모델)  
    
## **평가 및 고찰**
* 모델1개 > 모델2개  
  \- 홍채와 얼굴 데이터를 concatenate하여 하나의 벡터로 학습시킨 경우(모델1개)가 각 데이터를 따로 학습시킨 경우(모델2개)보다 높은 정확도를 보임  
  \- 더 많은 feature를 추출할 수 있기 때문으로 추측  
