# power-support

### 조작하는 값

배터리 사용
- `powercfg set`
  - `power-saver` == `power-saver` (유지)
  - `balanced` == `balanced` (유지)
  - `performance` -> `power-saver`

충전기 연결
- `powercfg set`
  - `power-saver` -> `performance`
  - `balanced` -> `performance`
  - `performance` == `performance` (유지)

### 사용법
1. docksupport 파일을 적당한 곳에 저장, chmod +x
2. 유저 서비스 등록

```commandline
sudo vi /etc/systemd/user/powersupport.service
```

```text : docksupport.service
[Unit]
Description=ThinkPad Adaptive Powermode Support

[Service]
ExecStart=/home/kh/.script/powersupport
Restart=always

[Install]
WantedBy=default.target
```
3. systemd 재시작 후 서비스 활성화
```commandline
systemctl --user daemon-reload
systemctl --user start powersupport.service
```