# AGV_Project
SSAFY 11기 AGV(무인운반로봇) 프로젝트

## 프로젝트 소개


인공지능 무인운반차량(AGV)으로 Road Following 을 하기 위해 데이터를 수집한다. 아래와 같은 map이 주어진다. 이 지도를 우선 어느 장소에 둘 지 고민한다. 추후에 해당 지도에 있는 색상 영역을 이용해서 인공지능 무인운반차량(AGV)이 Working Area 를 설정하고 움직이게 된다. 색상을 인식하는 방식은 map이 설치된 주변 환경에 예민할 수 있다. 가령, 창문을 통해서 들어오는 햇빛이나, 밝기가 너무 어두운 조명 아래에서는 원활한 감지가 안 될 수 있다. 그렇기 때문에, 최대한 외부의 영향을 덜 받고, map을 시시각각 움직이지 않아도 되는 장소에 설치하는 것을 권장한다. 또한, 인공지능 무인운반차량(AGV)이 예상치 못한 상황으로 인해 통제에서 벗어나도 쉽게 대응을 할 수 있고, 다른 사람에게 피해를 끼치지 않도록 사람이 많이 돌아다니지 않는 장소를 권장한다. 그럼 데이터 수집, 모델 학습, 학습된 모델 테스트를 통해 Road Following 을 구현하자.


![image](https://github.com/taekg/AGV_Project/assets/94892850/925f2fac-51b1-43bb-a1dc-47c0ac428fdc)


## 필수로 제작해야하는 세 가지 모듈


1. 인공지능과 Computer Vision을 이용하여 움직이는 인공지능 무인운반차량(AGV)
2. 원격으로 인공지능 무인운반차량(AGV)을 제어하는 GUI 원격 제어기
3. 서버리스 기반으로 인공지능 무인운반차량(AGV)과 GUI 원격 제어기의 통신을 담당하는 Cloud Database


### 2-1) 인공지능 무인운반차량(AGV)

인공지능 무인운반차량(AGV)의 가장 큰 역할은 인공지능과 Computer Vision을 이용하여 Working Area 사이에서 물류를 운반하는 역할이다. GUI 원격 제어기로 DB를 통해 command를 보내면, command 를 읽어서 동작을 수행한다. 창작 활동으로 다양한 센서를 덧붙여 GUI 원격 제어기에 sensing data 를 보낼 수 있다.


### 2-2) GUI 원격 제어기

GUI 원격 제어기는 Raspberry Pi 5 + Qt 로 만들어진다. 사용자 입력에 따라 인공지능 무인운반차량(AGV)을 원격으로 제어할 수 있다.
원격 제어기의 가장 중요한 역할은 스스로 통제 불능에 빠지거나 전혀 예상하지 못한 환경에 처한 인공지능 무인운반차량(AGV)을 다시 정상 상태로 복귀 시키는 것이다.  추가적으로 GUI 원격 제어기를 통해 인공지능 무인운반차량(AGV)으로부터 다양한 sensing data 와 Camera로 촬영한 화면 영상을 직접 보면서 인공지능 무인운반차량(AGV)의 현 상황을 체크할 수 있는 모니터의 역할도 수행할 수 있다.


### 2-3) Cloud Database

Cloud Database의 역할은 GUI 원격 제어기와 인공지능 무인운반차량(AGV)으로부터 받은 Data를 저장하고, 넘겨주는 역할이다. 우리는 Firebase 기반의 Cloud Database 를 운영하여 서버리스 방식으로 서버를 운영한다. 
