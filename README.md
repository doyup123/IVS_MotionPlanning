자율주행차의 경로 계획 및 제어 / ADAS Motion Planning & Control With Carmaker, MatLab&Simulink
===========
## 목차
- [프로젝트 개요](#프로젝트-개요)
- [세부목표](#세부목표)
- [FSM 기반 SW 아키텍처](#fsm-기반-sw-아키텍처)
- [시나리오 기반 TestCase 설계](#시나리오-기반-testcase-설계)
- [1. Driving Mode](#1-driving-mode)
- [2. Parking Mode](#2-parking-mode)
- [3. TestCase 기반 검증 수행 및 디버깅](#3-testcase-기반-검증-수행-및-디버깅)
- [시연 영상](#시연-영상)

## 프로젝트 개요

**주어진 트랙에서 도로 주행 이후 원하는 구역에 주차 한다.**

<img src="https://github.com/user-attachments/assets/3dae7c26-785d-429b-89f3-62edfcbe3cf6" width="480" />

|이름| 역할 | 프로젝트 기간|
|-----|------|----|
|김도엽  | 테스트 케이스 설계, SW 아키텍처 설계 , Global_path planning | 2025.05 ~ 2025.06|

|사용 Tool|MatLab & Simulink / CarMaker / Python|
|---|---|


## 세부목표
|세부 목표|내용|
|--------|-----|
|1. 차량 추월| <img src="https://github.com/user-attachments/assets/bd432eac-38bd-409b-bffe-0524858a1896" width="360" />|
|2. 원하는 톨게이트 통과 |<img src="https://github.com/user-attachments/assets/f50bf59f-d590-4899-a6df-d45cee91e771" width="360" />|
|3. 주차장 진입을 위한 차선 변경|<img src="https://github.com/user-attachments/assets/237a3b66-3807-4af7-b2bd-65fde9fb3ed2" width="360" />|
|4. 주차|<img src="https://github.com/user-attachments/assets/b18eea48-f5fd-4170-9daa-2d9ccf0174e5" width="360" />|

## FSM 기반 SW 아키텍처
목표 미션별 Mode를 다르게 하기 위해 FSM을 활용
|<img src="https://github.com/user-attachments/assets/1b17a7c2-2b82-4bd7-abb7-a4ead29db893" width="420" />|<img src="https://github.com/user-attachments/assets/17cd8ae7-e145-4781-bb7d-bcd829e20725" width="420" />|
|---|---|

## 시나리오 기반 TestCase 설계
<img src="https://github.com/user-attachments/assets/adec88ff-f293-4802-8a4e-3bbd04a851d9" width="720" />

## 1. Driving Mode
### 차량 추월 / 톨게이트 통과 / 차선 변경을 위한 Mode
<img src="https://github.com/user-attachments/assets/b35dc7ff-46ab-4388-ae0c-85259935c425" width="480" />

- **Global Path Planning**: 출발지점 → 목적지까지 **지도상 최적 경로**(정적·준정적 장애물 기준)
- **Local Path Planning**: 전역 경로 주변의 짧은 구간에서 실시간 장애물 변화를 반영한 **시간화된 실시간 궤적**

### 🌎 Global Path Planning 
<img src="https://github.com/user-attachments/assets/9d715dc8-1a16-4b09-8d59-ef6a32da80cd" width="480" />

- A* 알고리즘을 활용해 시작지점부터 목적지점 까지의 경로 생성

### 🚗 Local Path Planning
|Local Path Planning|<img src="https://github.com/user-attachments/assets/f98f9d09-d441-4765-b9d6-be2fe3e91e37" width="360" />|
|----|----|
|Cost Function| <img src="https://github.com/user-attachments/assets/87d59054-d3e5-416c-92a9-150a1fd94f1f" width="420" /> |

## 2. Parking Mode
|주차장 진입 경로 Global Path 생성| <img src="https://github.com/user-attachments/assets/78f0b2d7-1e9c-45c8-8833-3441e5968a2c" width="540" /> |
|---|---|
|주차 경로 생성| <img src="https://github.com/user-attachments/assets/0f4323a2-82de-4db5-95b0-9e7de6028a43" width="540" /> |

## 3. TestCase 기반 검증 수행 및 디버깅
|<img src="https://github.com/user-attachments/assets/3d2b01c2-e557-4003-82c4-18c1d53cf00a" width="420" />|<img src="https://github.com/user-attachments/assets/f0b46dad-c97e-4686-8635-0448c8bf7d80" width="420" />|
|---|---|

## 시연 영상
https://youtu.be/TwMqGNApJog
