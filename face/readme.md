# 얼굴 인식 (face recognition)
## **트레이닝 데이터셋 :**
  * 1명당 3개씩, 350명의 대한 얼굴 데이터, 총 1,050개의 얼굴 데이터   
  * 크기 : 46*56px  
    <img src="https://user-images.githubusercontent.com/58112670/151302855-b68353ac-9e5f-4693-b9ea-bcb0cbca9989.png" width="300">

## **사용 기법 :**
  * 데이터 전처리 :  
    \- 레이블 원핫인코딩  
    \- 픽셀 정규화  
    ```
    img_array = cv.imread(os.path.join(path, img))/255.0
    ```
   
  * 모델 아키텍쳐 :   
    \- CNN기반 딥러닝
    ```
    model = models.Sequential()  # 레이어를 층층히 쌓아가는 연쇄 모델

    model.add(layers.Conv2D(filters = 32, kernel_size = (3,3), padding='Same', activation='relu'))
    model.add(layers.MaxPooling2D(pool_size = (2,2)))
    model.add(layers.Dropout(0.1))

    model.add(layers.Conv2D(filters = 32, kernel_size = (3,3), padding='Same', activation='relu'))
    model.add(layers.MaxPooling2D(pool_size = (2,2)))
    model.add(layers.Dropout(0.1))

    model.add(layers.Conv2D(filters = 128, kernel_size = (3,3), padding='Same', activation='relu'))
    model.add(layers.MaxPooling2D(pool_size = (2,2)))

    model.add(layers.Flatten())
    model.add(layers.Dense(312, kernel_initializer='he_normal'))
    model.add(layers.BatchNormalization())
    model.add(layers.Dense(350, activation='softmax'))
    ```
  * 모델 컴파일 :  
    \- 최적화 함수 : adam  
    \- loss function : categorical_crossentropy  

## **성능 :**  
  * 정확도 :   
    <img src="https://user-images.githubusercontent.com/58112670/151309842-773ecb1d-beee-4174-9378-0974af645d6e.PNG" width="200">
