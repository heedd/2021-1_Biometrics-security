# 멀티모달 인식 (multimodal recognition)
## **과제 목적 :**
  * 얼굴과 홍채를 각각 인식하는 각각의 모델 구현 (총 2개의 모델)  
    * 입력 :  
      \- 얼굴 인식 모델 : [얼굴] → [어떤 사람 F]  
      \- 홍채 인식 모델 : [홍채] → [어떤 사람 I]  
    * 출력 :  
      \- [F], [I] → [어떤 사람?]  <br/>
      <img src="https://user-images.githubusercontent.com/58112670/151374532-8637b249-b167-415a-9e44-4c8f3c9e714f.png" width="300">  <br/><br/>
      
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
(1) face_model : 얼굴인식 모델  
  * 모델 아키텍쳐 :  
    \- CNN기반 딥러닝  
    <img src="https://user-images.githubusercontent.com/58112670/151373678-281adce6-cd18-4e61-a0d7-773ce963c7c2.png" width="300">  <br/><br/>

(2) iris_model : 홍채인식 모델  
  * 모델 아키텍쳐 :  
    \- CNN기반 딥러닝  
    <img src="https://user-images.githubusercontent.com/58112670/151373747-59a811b3-16ea-483e-b460-5c95baa0f1c1.png" width="300">  <br/><br/>
    
(3) concat_model : face_model과 iris_model 모델 병합
  * 모델 아키텍쳐 :  
    \- face_model과 iris_model의 출력을 입력으로 받는 최종 dense layer   
    <img src="https://user-images.githubusercontent.com/58112670/151374033-00af3700-9482-452e-8d34-3c4ea7afbdaf.png" width="300">  <br/><br/>

## **성능 :**  
  * 정확도 :   
    <img src="https://user-images.githubusercontent.com/58112670/151374124-82c3a4dc-d7a4-473c-90ca-042f56c81371.png" width="200">
