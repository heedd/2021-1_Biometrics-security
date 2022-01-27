# 멀티모달 인식 (multimodal recognition)
## **과제 목적 :**
  * 얼굴과 홍채를 각각 인식하는 각각의 모델 구현 (총 1개의 모델)  
    * 입력 : [얼굴, 홍채]  
    * 출력 : [어떤 사람?]  <br/><br/>
      
## **트레이닝 데이터셋 :**
(1) 얼굴
  * 1명당 얼굴 데이터 4개, 64명의 대한 데이터, 총 512개의 데이터  
  * 크기 : 786*576px  
  * 데이터 증강 : 수직, 수평 이동, 밝기 조절하여 총 2048개 데이터 훈련  
    
(2) 홍채
  * 1명당 홍채 데이터 4개, 64명의 대한 데이터, 총 512개의 데이터  
  * 크기 : 46*56px  
  * 데이터 증강 : 수직, 수평 이동, 밝기 조절하여 총 2048개 데이터 훈련  <br/>
    <img src="https://user-images.githubusercontent.com/58112670/151369766-01ba419a-3bb0-4b58-8fcf-8c138ac4dc14.png" height="200"> <img src="https://user-images.githubusercontent.com/58112670/151369782-64a94b0b-d877-4698-a18c-bc1281b8a6eb.png" height="200">  <br/><br/>

## **사용 기법 :**
  * 데이터 전처리 :  
    \- 얼굴 · 홍채 Concatenate : 얼굴과 홍채 이미지를 하나의 벡터로 합성  
    얼굴과 홍채를 하나의 벡터로 만들기 위해 (43, 48, 3)으로 resize  
    Face resize시 보간법의 영향을 최소화하기 위해 transpose  
    크기가 같은 face와 iris 이미지 concatenate하여 저장  <br/>
    <img src="https://user-images.githubusercontent.com/58112670/151378400-d763555f-62dc-448c-9259-e5e1a28356fe.png" width="300">  <br/>

  * 모델 아키텍쳐 :   
    \- CNN기반 딥러닝  
    <img src="https://user-images.githubusercontent.com/58112670/151377969-e39479ad-90fb-4bf7-9533-566699990225.png" width="300">  <br/>

  * 모델 컴파일 :  
    \- 최적화 함수 : adam  
    \- loss function : categorical_crossentropy  <br/>
    
## **성능 :**  
  * 정확도 :   
    <img src="https://user-images.githubusercontent.com/58112670/151377801-79c51c1f-9f6e-44e1-8198-5e19a0f3cc76.png" width="200">
