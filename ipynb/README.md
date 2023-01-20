### 1a_dicom 
  dicom 헤더 파일을 통해서 일괄적으로 파일명을 변경
  
### 1b_meta
  각종 파일 데이터클리닝 & 분석에 활용한 자료 만들기  
  Density reading이 완료된 자료를 바탕으로 DICOM 파일과 매칭
  
### 2a_process 
  분석에 적절한 이미지 선정 및 전처리 실시
  
### 2b_resize 
원하는 사이즈로 일괄 변경 (256x256)

### 3_train  
  desity label이 있는 것 이미지를 대상으로 train set, validation set, test set 생성   
  control에서 좌우 둘다 있는 경우 한 쪽만 선택, case에서는 발병 반대쪽을 선택
  
### 3a_train_density-unet 
  **monai package**를 활용하여 **U-Net**으로 train
  
### 3b_trainimage 
  **Dense121** 사용하여 Occlusion sensitivity를 계산
  
### 4_test 
  dataset에서 학습에 사용되지 않은 데이터에 대해서 모델을 적용하여 test
  
### 4a_predict_xgboost 
  calibration set을 활용하여 **xgboost model** 생성
