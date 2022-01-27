# 얼굴 인식 (face recognition)
* **트레이닝 데이터셋 :**  
  \- 1명당 3개씩, 350명의 대한 얼굴 데이터, 총 1,050개의 얼굴 데이터  
  \- 크기 : 46*56 px  
<img src="https://user-images.githubusercontent.com/58112670/151302855-b68353ac-9e5f-4693-b9ea-bcb0cbca9989.png" width="500">
  
* **사용 기법 :**  
  \- 데이터 전처리 :  
  픽셀 정규화  
  레이블 원핫인코딩  
   
  \- 모델 아키텍쳐 :  
  Conv2D, MaxPooling2D, Dropout 레이어와 활성화 함수 relu를 사용  
  출력을 위해 Flatten레이어로 1차원으로 변환 후 he_normal, batch normalization  
  다중 클래스 분류에 적합한 softmax 활성화함수 사용하여 분류 결과 도출  
  
  \- 모델 컴파일 :  
  최적화 함수 : adam  
  loss function : categorical_crossentropy  

* **성능 :**  
  \- 정확도 :   
![face_res](https://user-images.githubusercontent.com/58112670/151303444-5c36d2ec-de08-4085-be23-742bbecab915.PNG)
