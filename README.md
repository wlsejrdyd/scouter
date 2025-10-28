# 🛠 넥서스커뮤니티 스카우터 개발 프로젝트

고객사 서버 리소스 및 소켓, 연결자수 확인 및 쿼리 트레이싱.<br>
기존 배포되어있는 소스에 추가 적인 개발을 하기위해 만들어졌습니다.

필요 소스들만 압축해서 사용 가능하지만, 스크립트 정상 동작을 위해 압축시
tar cvfz jdy-scouter.tgz ./server ./agent.host ./jdk 와 같은 명령어로 압축 바랍니다. 
압축 파일 이름에**jdy-scouter** 이름으로 시작하면 됩니다.
Ex) jdy-scouter-1.0.0.tgz

---

## 🚀 기술 스택

- JDK 1.8
- Slack WebHook 플러그인 추가
- Server/Collector (scouter-server)
- Agent-Host (scouter-host)
- Agent-Java
- install shell script ("scouter_install_$(cat version).sh")

---

## 📌 버전 히스토리

### script
| 버전   | 주요 기능 |
|--------|-----------|
| v0.1   | server 설치,설정,실행,방화벽 허용 정책 적용 <br> agent.host 설치,설정,실행 <br> agent.java 설정 | 
| v0.2   | 서비스 설치 기본 디렉터리 변경 (/home/scoutersvc/scouter) <br> 경로 변경에 따른 설정 파일 및 스크립트 수정 <br> 방화벽 동작 기능 제거 <br> find 명령어 사용 시 사용자가 직접 선택 후 동작하도록 변경 <br> agent.java 톰캣 다중 인스턴스 환경에서 동작 가능하도록 수정 <br> 신규 오류 건 처리 |
| **v0.3** | 서비스 계정 scoutersvc => apm 변경 <br> 한글 출력 깨짐 방지 추가 <br> host agent disk 임계치 수정 및 디스크 alert counter 시간 1시간에서 10분으로 변경  |

### scouter server
| 버전   | 주요 기능 |
|--------|-----------|
| v1.0   | 기본 패키지 사용 |

### scouter host
| 버전   | 주요 기능 |
|--------|-----------|
| v1.0   | 기본 패키지 사용 |
| v1.1   | cpu,mem,disk 임계치 80/90 (warning/fatal) 조정 <br> disk alert interval time 1시간 -> 10분으로 변경 |

### scouter java
| 버전   | 주요 기능 |
|--------|-----------|
| v1.0   | 기본 패키지 사용 |


## 🧩 향후 계획 (v0.3 ~ )

- NEXUS 제품의 데이터 모니터링 개발
- 기본 제공 메트릭 외 추가 확장 가능성 확인 및 개발
