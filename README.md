# 🚗 Advanced Deep-Learning RCPI Car

![Python](https://img.shields.io/badge/Python-3.x-blue.svg)
![TensorFlow](https://img.shields.io/badge/TensorFlow-Keras-orange.svg)
![OpenCV](https://img.shields.io/badge/OpenCV-DNN-brightgreen.svg)
![Raspberry Pi](https://img.shields.io/badge/Raspberry%20Pi-Hardware-red.svg)

라즈베리 파이(Raspberry Pi) 기반의 **딥러닝 자율주행 및 객체 인식 충돌 방지 RC카 프로젝트**입니다. 
CNN 모델을 통한 '차선 유지 자율주행'과 OpenCV DNN(MobileNet SSD)을 활용한 '실시간 보행자 인식 및 자동 정지' 기능이 다중 스레드(Multi-threading)로 동시에 작동하여 더욱 안전하고 스마트한 주행을 구현했습니다.

## ✨ 핵심 기능 (Key Features)

- **End-to-End 자율주행**: 수집된 주행 이미지를 학습한 Keras 딥러닝 모델이 실시간으로 조향각을 예측하여 차선을 따라 주행합니다.
- **실시간 객체 인식 (MobileNet SSD)**: 주행 중 카메라 영상을 분석하여 사람(Person) 등 특정 객체를 탐지합니다.
- **자동 긴급 제동 (Auto-Stop)**: 장애물이나 보행자가 인식되면 즉시 모터를 정지하여 충돌을 방지합니다.
- **다중 스레딩 (Multi-threading)**: 자율주행 조향 로직과 무거운 객체 인식(DNN) 로직을 별도의 스레드로 분리하여 병목 현상 없이 부드러운 주행을 보장합니다.

## 📂 프로젝트 구조 (Project Structure)

```text
Deep-Learning-RCPI-Car/
 ├── README.md                              # 프로젝트 설명서
 ├── data_collection.py                     # 수동 조종 및 주행 데이터(이미지/조향각) 수집
 ├── make_model_for_docker.ipynb            # 데이터 전처리 및 CNN 자율주행 모델 학습 (Jupyter)
 ├── autonomous_drive.py                    # 차선 유지 기본 자율주행 스크립트
 ├── auto_drive_with_detection.py           # 자율주행 + 객체 인식(보행자 자동 정지) 스크립트
 ├── model/                                 
 │   └── lane_navigation_final.h5           # Keras 자율주행 학습 모델
 ├── OpencvDnn/models/                      # OpenCV 객체 인식 사전 학습 모델 (MobileNet SSD)
 │   ├── frozen_inference_graph.pb          
 │   └── ssd_mobilenet_v2_coco_2018_03_29.pbtxt
 └── video/                                 # 수집된 주행 이미지 데이터 보관소