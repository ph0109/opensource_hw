# 🖥️[과제2] README 파일 작성하기
리눅스 명령어 중에서 top, ps, jobs, kill 명령어에 대해서 조사해보기

## 📌top
시스템의 실시간 성능을 모니터링할 수 있는 강력한 도구입니다.

top 명령어를 실행하면 현재 시스템에서 실행 중인 프로세스와 그들의 CPU 및 메모리 사용량, 시스템 부하 등을 실시간으로 확인할 수 있습니다. 

### 주요 기능
- 실시간 시스템 모니터링: CPU, 메모리, 스왑 사용량 등 시스템 리소스를 실시간으로 모니터링합니다. 
- 프로세스 정보 제공: 현재 실행 중인 프로세스의 PID, 사용자, 우선순위, CPU 및 메모리 사용률 등을 보여줍니다.
- 프로세스 관리: top 인터페이스에서 직접 프로세스를 종료하거나 우선순위를 변경할 수 있습니다.

### 주요 출력 항목
- 시스템 정보: 화면 상단에 시스템의 현재 시간, 시스템 가동 시간, 로그인된 사용자 수, 시스템 부하 평균 (1, 5, 15분) 등이 표시됩니다. 
- 작업(Task) 요약: 현재 실행 중인 프로세스 수, 중지된 프로세스 수, 좀비 프로세스 수 등을 보여줍니다. 
- CPU 상태: 사용자, 시스템, 나이스, 아이들, IO 대기 등 CPU 사용률을 표시합니다.
- 메모리 상태: 총 메모리, 사용 중인 메모리, 사용 가능한 메모리, 스왑 메모리 등을 보여줍니다.
- 프로세스 목록: PID, 사용자, 우선순위, nice 값, 가상 메모리 사용량, 실제 메모리 사용량, 공유 메모리 사용량, CPU 사용률, 메모리 사용률, 실행 시간, 명령어 등을 포함한 프로세스 리스트를 보여줍니다.

### 예시본
![image](https://github.com/ph0109/opensource_hw/assets/132151797/f0e89c1a-014b-48bd-8af3-173cdb693fad)
<img src = "https://github.com/ph0109/opensource_hw/assets/132151797/f0e89c1a-014b-48bd-8af3-173cdb693fad" width="100" height = "50">
## 📌ps
현재 실행중인 프로세스에 대한 정보를 보여줍니다. 

사용자는 이를 통해 시스템에서 실행 중인 프로세스의 상태, 사용자의 ID, CPU 사용량 등 다양한 정보를 얻을 수 있습니다. 

ps 명령어는 다양한 옵션들을 조합하여 사용할 수 있으며, 사용자의 요구에 맞는 세밀한 정보를 제공합니다. 

### 기본 사용법
- ps [옵션]

### 주요 옵션
- -e: 시스템상의 모든 프로세스 정보를 출력.
- -f: 풀 포맷으로 보여줍니다. UID, PID, PPID, C, STIME, TTY, TIME, CMD 등의 정보가 포함.
- -u [사용자명]: 지정한 사용자의 프로세스 정보를 출력.
- -p [PID]: 특정 PID(프로세스 ID)의 프로세스 정보를 출력.
- -aux: 시스템상의 모든 사용자의 모든 프로세스 정보를 사용자 친화적 형태로 출력. 이 옵션은 BSD 스타일이며, 리눅스에서 널리 사용됨.

### 출력 정보
- PID: 프로세스 ID
- TTY: 프로세스가 연결된 터미널
- TIME: CPU 시간의 총 사용량
- CMD: 프로세스를 시작한 명령
- UID: 프로세스를 실행한 사용자 ID
- PPID: 부모 프로세스 ID
- C: CPU 사용량

## 📌jobs
현재 쉘 세션에서 실행중이거나 정지된 백그라운드 작업의 목록을 보여줍니다. 

이 명령어는 사용자가 백그라운드에서 실행 중인 작업을 관리할 수 있도록  도와주며, 작업의 상태, 작업 번호, 명령어 등의 정보를 제공합니다. 


### 작업 상태
- Running: 작업이 실행 중임을 나타냅니다. 
- Stopped: 작업이 일시 정지되었음을 나타냅니다.
- Done: 작업이 완료되었음을 나타냅니다.

### 기본 사용법
```
jobs [옵션] [작업번호...]
```

### 주요 옵션
- -l: 프로세스 그룹 ID를 포함한 상세 정보를 출력
- -n: 프로세스 그룹 중 대표 프로세스 ID만을 출력
- -p: 각 작업에 대한 프로세스 ID만을 출력
- -r: 실행 중인 작업만을 출력
- -s: 정지된 작업만을 출력

## 📌kill
Linux에서 kill 명령어는 프로세스에 신호를 보내는 데 사용됩니다. 

주로 프로세스를 종료시키기 위해 사용되며, 시스템에서 실행 중인 프로세스를 관리하는데 필수적인 도구입니다. 

사용자는 kill 명령어를 통해 특정 프로세스에 다양한 종류의 신호를 보낼 수 있으며, 이 신호들은 프로세스에 다양한 동작을 수행하도록 지시할 수 있습니다. 

### 기본 사용법 
```
kill [옵션] <프로세스ID>
```

### 자주 사용되는 신호
- SIGTERM (15): 프로세스에게 종료할 것을 요청하는 기본 신호
                이 신호는 프로세스가 정상적으로 종료할 수 있도록 기회를 제공.
- SIGKILL (9): 프로세스를 즉시 종료시키는 신호
               이 신호는 프로세스에게 종료 준비를 할 수 있는 기회를 주지 않음. 
               SIGKILL은 거의 모든 상황에서 프로세스를 종료시킬 수 있지만, 시스템이 깨끗하게 종료되지 않을 수 있으므로 신중해야함. 
- SIGSTOP (19): 프로세스를 일시 정지시키는 신호
                이 신호는 SIGCONT 신호를 받을 때까지 프로세스를 정지시킴. 
