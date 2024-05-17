### 1. SD 카드 포맷

### 2. jetbot image 다운로드

`https://jetbot.org/master/software_setup/sd_card.html`

Old releases 의 Jetson Nano(4GB) JetPack Version 4.3 , JetBot Version 0.4.0 으로 다운 진행

### 3. SD카드에 image 설치

아래 링크에서 SD카드에 image 파일을 설치할 수 있도록 해주는 Etcher 프로그램을 설치한다.

`https://etcher.balena.io/#download-etcher`

### 4. putty로 UART 접속

아래 링크에서 putty를 다운받아 설치한다.
`https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html`

Serial접속을 선택하고 port 번호를 입력한 뒤 Open

#### 4-1. 인터넷 설정
`sudo nmcli device wifi connect [SSID] password [PASSWORD]`

#### 4-2. JETANK 설치
`git clone https://github.com/waveshare/JETANK.git`

`cd JETANK`
`chmod +x config.sh`
`./config.sh jetbot`

reboot 후에 LCD에 연결된 IP주소 확인

### 5. Jupyter Notebook 접속

### 6. ServoInt 설치

터미널에서 아래와 같이 입력한다.
`cd JETANK/`
`./install.sh`
`sudo python3 servoInt.py`
