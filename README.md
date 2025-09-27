자율주행차의 경로 계획 및 제어 / ADAS Motion Planning & Control With Carmaker, MatLab&Simulink
===========
## 프로젝트 개요
주어진 트랙에서 도로 주행 이후 원하는 구역에 주차 한다.
<img width="610" height="405" alt="image" src="https://github.com/user-attachments/assets/3dae7c26-785d-429b-89f3-62edfcbe3cf6" />

|이름| 역할 | 프로젝트 기간|
|-----|------|----|
|김도엽  | 테스트 케이스 설계, SW 아키텍처 설계 , Global_path planning | 2025.05 ~ 2025.06|

## 세부목표
|세부 목표|내용|
|--------|-----|
|1. 차량 추월| <img width="499" height="319" alt="image" src="https://github.com/user-attachments/assets/bd432eac-38bd-409b-bffe-0524858a1896" />|
|2. 원하는 톨게이트 통과 |<img width="508" height="304" alt="image" src="https://github.com/user-attachments/assets/f50bf59f-d590-4899-a6df-d45cee91e771" />|
|3. 주차장 진입을 위한 차선 변경|<img width="457" height="299" alt="image" src="https://github.com/user-attachments/assets/237a3b66-3807-4af7-b2bd-65fde9fb3ed2" />|
|4. 주차|<img width="473" height="295" alt="image" src="https://github.com/user-attachments/assets/b18eea48-f5fd-4170-9daa-2d9ccf0174e5" />|

## FSM 기반 SW 아키텍처
목표 미션별 Mode를 다르게 하기 위해 FSM을 활용 
|<img width="953" height="505" alt="image" src="https://github.com/user-attachments/assets/1b17a7c2-2b82-4bd7-abb7-a4ead29db893" />|<img width="867" height="483" alt="image" src="https://github.com/user-attachments/assets/17cd8ae7-e145-4781-bb7d-bcd829e20725" />|
|---|---|


## 시나리오 기반 TestCase 설계
<img width="1233" height="654" alt="image" src="https://github.com/user-attachments/assets/adec88ff-f293-4802-8a4e-3bbd04a851d9" /> 


## 1. Driving Mode 
### 차량 추월 / 톨게이트 통과 / 차선 변경을 위한 Mode
![driving-mode](https://github.com/user-attachments/assets/b35dc7ff-46ab-4388-ae0c-85259935c425)

- **Global Path Planning**: 출발지점 → 목적지까지 **지도상 최적 경로**(정적·준정적 장애물 기준)
- **Local Path Planning**: 전역 경로 주변의 짧은 구간에서 실시간 장애물 변화를 반영한 **시간화된 실시간 궤적**

### Global Path Planning
<img width="751" height="424" alt="image" src="https://github.com/user-attachments/assets/9d715dc8-1a16-4b09-8d59-ef6a32da80cd" />

- A* 알고리즘을 활용해 시작지점부터 목적지점 까지의 경로 생성

### Local Path Planning

|Local Path Planning|<img width="645" height="304" alt="image" src="https://github.com/user-attachments/assets/f98f9d09-d441-4765-b9d6-be2fe3e91e37" />|
|----|----|
|Cost Function| <img width="700" height="354" alt="image" src="https://github.com/user-attachments/assets/87d59054-d3e5-416c-92a9-150a1fd94f1f" /> |

## 2. Parking Mode
|주차장 진입 경로 Global Path 생성| <img width="824" height="343" alt="image" src="https://github.com/user-attachments/assets/78f0b2d7-1e9c-45c8-8833-3441e5968a2c" /> |
|---|---|
|주차 경로 생성| <img width="918" height="354" alt="image" src="https://github.com/user-attachments/assets/0f4323a2-82de-4db5-95b0-9e7de6028a43" /> |








