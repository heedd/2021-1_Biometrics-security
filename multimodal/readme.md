# 멀티모달 인식 (multimodal recognition)
## **멀티모달 러닝(multimodal learning)**
* 다양한 차원의 데이터의 특징을 효과적으로 학습하기 위한 방법  

## **과제 목적**
  [(1) 모델 1개](https://github.com/heedd/2021-1_Biometrics-security/tree/master/multimodal/%EB%AA%A8%EB%8D%B8%201%EA%B0%9C) 
    : 얼굴과 홍채를 각각 인식하는 각각의 모델 구현 (총 1개의 모델)  
  [(2) 모델 2개](https://github.com/heedd/2021-1_Biometrics-security/tree/master/multimodal/%EB%AA%A8%EB%8D%B8%202%EA%B0%9C) 
    : 얼굴과 홍채를 각각 인식하는 각각의 모델 구현 (총 2개의 모델)  
    
## **평가 및 고찰**
* 모델1개 > 모델2개  
  \- 홍채와 얼굴 데이터를 concatenate하여 하나의 벡터로 학습시킨 경우(모델1개)가 각 데이터를 따로 학습시킨 경우(모델2개)보다 높은 정확도를 보임  
  \- 더 많은 feature를 추출할 수 있기 때문으로 추측  
  
  
