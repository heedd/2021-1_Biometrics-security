# 홍채 인식 (iris recognition)
## **트레이닝 데이터셋 :**
  * 데이터 증강 : 
    \- 원본 : 1명당 2개씩, 64명의 대한 홍채 데이터, 총 128개의 홍채 데이터
    \- 수직, 수평 방향으로 이동시키거나 밝기 변화
    \- 원본 이미지 2개를 포함하여 레이블 당 총 18개의 이미지를 학습할 수 있도록 데이터 증강
    \- 최종 학습데이터 : 1명당 18개씩, 64명의 대한 홍채 데이터, 총 2304개의 홍채 데이터
  * 크기 : 768*576px  
    <img src="https://user-images.githubusercontent.com/58112670/151314706-4b202061-0cb2-4196-89fb-a55f6af1105f.png" width="300">
    <img src="https://user-images.githubusercontent.com/58112670/151319132-824315c9-27fa-40b0-b83f-eafd0c226f71.png" width="270">  

## **사용 기법 :**
  * 데이터 전처리 :  
    \- 레이블 원핫인코딩  
    \- 이미지 트리밍 : 속눈썹, 눈꺼풀 등 홍채 인식에 필요 없는 부분을 제거  
    <img src="https://user-images.githubusercontent.com/58112670/151314921-37bcea63-d0e6-49a7-ac9f-353fd6f3323f.png" width="300">  
    ~~\- ROI (Region of Interest; 관심영역) :  cv2.HoughCircles을 이용하여 원본에서 원형의 이미지를 검출  (tilde)~~
    <img src="https://user-images.githubusercontent.com/58112670/151315015-3d074ece-6007-44a0-82c3-0d79dcb4cd44.png" width="300">  
    \- 이미지 resize 및 정규화  
    ```
    img_array = cv.imread(os.path.join(path, img))/255.0
    img_array = cv.resize(img_trim(img_array), (0,0), fx=0.1, fy=0.1)
    ```
  * 모델 아키텍쳐 :   
    \- CNN기반 딥러닝  
    <img src="https://user-images.githubusercontent.com/58112670/151316810-c83b118a-eab7-4a42-86fc-504c57af1bbd.png" width="300">
    
  * 모델 컴파일 :  
    \- 최적화 함수 : adam  
    \- loss function : categorical_crossentropy  

## **성능 :**  
  * 정확도 :   
    <img src="https://user-images.githubusercontent.com/58112670/151319477-548692d7-d2da-4175-9605-9ec582459002.png" width="200">
