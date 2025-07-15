# pmode-support

### 조작하는 값

배터리 사용 <-> 충전기 연결
- pmodeup
  - `powercfg set`
    - `power-saver` -> `balanced` -> `performance` -> ...
- pmodedown
  - `powercfg set`
    - `performance` -> `balanced` -> `power-saver` -> ...

### 사용법
1. docksupport 파일을 적당한 곳에 저장, chmod +x
2. 단축키 등록
   - up
     - Name : `pmodeup`
     - Command : `/home/kh/.script/pmodeup`
     - Shortcut : `ctrl` + `bs`
   - down
     - Command : `pmodedown`
     - Command : `/home/kh/.script/pmodedown`
     - Shortcut`shift` + `ctrl` + `bs`