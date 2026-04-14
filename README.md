# 🚗 Deep-Learning-RCPI-Car

![Python](https://img.shields.io/badge/Python-3.x-blue.svg)
![TensorFlow](https://img.shields.io/badge/TensorFlow-Keras-orange.svg)
![OpenCV](https://img.shields.io/badge/OpenCV-Image_Processing-brightgreen.svg)
![Raspberry Pi](https://img.shields.io/badge/Raspberry%20Pi-Hardware-red.svg)

라즈베리 파이(Raspberry Pi)와 딥러닝(Deep Learning)을 활용한 **자율주행 RC카 프로젝트**입니다. 
사용자가 직접 조종하며 주행 데이터를 수집하고, 이를 바탕으로 인공지능 모델을 학습시켜 카메라 영상만으로 차선을 인식하고 스스로 주행(자율주행)할 수 있도록 구현되었습니다.

## 📂 프로젝트 구조 (Project Structure)

```text
Deep-Learning-RCPI-Car/
 ├── README.md                          # 프로젝트 설명서
 ├── autonomous_drive.py                # 학습된 모델을 이용한 실시간 자율주행 실행 파일
 ├── data_collection.py                 # 수동 조종 및 주행 이미지/조향각 데이터 수집 파일
 ├── make_model_for_docker.ipynb        # 수집된 데이터 전처리 및 CNN 모델 학습용 주피터 노트북
 ├── model/                             # 학습된 AI 모델 저장 폴더
 │   └── lane_navigation_final.h5       # 자율주행 조향각 예측 모델
 └── video/                             # data_collection.py로 수집한 주행 이미지 데이터 폴더