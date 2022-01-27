# 지문 인식 (fingerprint recognition)
## **트레이닝 데이터셋 :**
  * 1명당 10개씩, 8명의 대한 지문 데이터, 총 80개의 지문 데이터   
  * 크기 : 144*144px  
    <img src="https://user-images.githubusercontent.com/58112670/151306811-7778cf68-2aec-46bf-b289-d342a435c686.png" width="300">

## **사용 기법 :**
  * 데이터 전처리 :  
    \- 레이블 원핫인코딩  
    \- 이미지 트리밍 : 불필요한 부분 제거  
    <img src="https://user-images.githubusercontent.com/58112670/151306733-7b0b994e-fcff-4151-bc75-6f46dd740c3b.png" width="300">

   
  * 모델 아키텍쳐 :   
    \- CNN기반 딥러닝
    ```
    model = models.Sequential()  # 레이어를 층층히 쌓아가는 연쇄 모델

    model.add(layers.Conv2D(filters = 32, kernel_size = (3,3), padding='Same', activation='relu'))
    model.add(layers.MaxPooling2D(pool_size = (2,2)))
    model.add(layers.Dropout(0.1))

    model.add(layers.Conv2D(filters = 64, kernel_size = (3,3), padding='Same', activation='relu'))
    model.add(layers.MaxPooling2D(pool_size = (2,2)))
    model.add(layers.Dropout(0.1))

    model.add(layers.Flatten())
    model.add(layers.Dense(100,activation='relu'))
    model.add(layers.Dropout(0.3))
    model.add(layers.Dense(8, activation='softmax'))
    ```
    
  * 모델 컴파일 :  
    \- 최적화 함수 : adam  
    \- loss function : categorical_crossentropy  

## **성능 :**  
  * 정확도 :   
    <img src="https://user-images.githubusercontent.com/58112670/151307252-f35ff31b-6755-4a98-9e37-4cbb4e7ecacd.png" width="200">
