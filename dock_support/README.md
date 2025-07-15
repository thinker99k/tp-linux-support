# dock_support

### 상황

노트북 하나 들고다니면서 가는 곳마다 있는 독에 꼽고 사용하는데 해상도, 스케일링이 지멋대로임
- 집
  - 모니터
    - 24" 1920*1080 (스케일 100%)
    - 19" 1280*1024 (스케일 100%)
  - 마우스
    - 유선 (감도 -0.5)
- 밖 (노트북 네이티브)
  - 모니터
    - 16" 1920*1200 (스케일 100%)
  - 마우스
    - 트랙포인트 (감도 -0.5)
- **연구실**
  - 모니터
    - 32" 3840*2160 (**스케일 175%**)
    - 32" 3840*2160 (**스케일 175%**)
  - 마우스
    - 무선 (**감도 0.0**)


### 조작하는 값
기타 <-> **연구실** 

- `org.gnome.desktop.interface`
  - `text-scaling-factor`
    - `1.00` <-> **`1.75`**
- `org.gnome.shell.extensions.dash-to-dock`
  - `dash-max-icon-size`
    - `20` <-> **`48`**
- `set org.gnome.desktop.peripherals.mouse`
  - `speed`
    - `-0.5` <-> **`0.0`**

필요에 따라 다른 값들도 찾아서 스크립트 내 환경 변수로 추가하여 개조할 수 있을듯?  

### 사용법
1. docksupport 파일을 적당한 곳에 저장
2. 유저 서비스 등록

```commandline
sudo vi /etc/systemd/user/docksupport.service
```

```text : docksupport.service
[Unit]
Description=ThinkPad Thunderbolt Docking Station Support

[Service]
ExecStart=/home/kh/.script/docksupport
Restart=always

[Install]
WantedBy=default.target
```
3. systemd 재시작 후 서비스 활성화
```commandline
systemctl --user daemon-reload
systemctl --user start docksupport.service
```
---
xorg든 wayland든 쓰레기인듯.. 