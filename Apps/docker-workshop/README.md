# Docker Compose 워크샵 - 2일차 실습 자료 📚

원광대학교 컴퓨터공학과 Docker Compose 강의 2일차 워크샵 자료입니다.

## 📋 목차

1. [워크샵 개요](#-워크샵-개요)
2. [파일 구성](#-파일-구성)
3. [학습 목표](#-학습-목표)
4. [진행 방법](#-진행-방법)
5. [실습 순서](#-실습-순서)
6. [완료 확인](#-완료-확인)
7. [문제 해결](#-문제-해결)

---

## 🎯 워크샵 개요

이 워크샵은 **실습 중심**으로 진행됩니다!

- **학습 방식**: 객관식 문제를 풀면서 docker-compose 파일의 빈칸 채우기
- **난이도**: 기초 → 중급 → 도전 과제
- **목표**: 4개의 실제 앱을 직접 작성하면서 Docker Compose 완전 이해
- **보상**: 전체 프로젝트 완료 시 조기 퇴실! 🎉

---

## 📁 파일 구성

```
docker-workshop/
├── 00-questions.md                 # 📝 객관식 문제 모음
├── 01-complete-example.yml         # 📖 복습용 완전한 예제 (주석 풍부)
├── 02-qbittorrent-exercise.yml     # 🔰 실습 1: qBittorrent (18개 빈칸)
├── 03-convertx-exercise.yml        # 🔸 실습 2: ConvertX (15개 빈칸)
├── 04-filebrowser-exercise.yml     # 🔹 실습 3: FileBrowser (12개 빈칸)
├── 05-stirling-pdf-exercise.yml    # 🚀 실습 4: Stirling PDF (16개 빈칸, 도전!)
└── README.md                       # 📚 이 파일
```

---

## 🎓 학습 목표

이 워크샵을 마치면 다음을 할 수 있게 됩니다:

### 1️⃣ 기본 개념 완벽 이해
- ✅ Docker Compose 파일 구조
- ✅ services, volumes, environment 설정
- ✅ 이미지 태그와 버전 관리

### 2️⃣ CasaOS 특화 지식
- ✅ NSL Router 통합 (expose vs ports)
- ✅ 권한 관리 (PUID/PGID)
- ✅ 볼륨 매핑 전략 (/DATA 구조)
- ✅ x-casaos 메타데이터 작성

### 3️⃣ 실전 응용 능력
- ✅ 다양한 앱 유형 이해 (다운로더, 유틸리티, 파일 관리자 등)
- ✅ 리소스 관리 (cpu_shares, memory limits)
- ✅ 다국어 지원 구현
- ✅ 보안 설정 (로그인, 권한, pre-install-cmd)

---

## 🚀 진행 방법

### Step 1: 복습하기 (15분)
`01-complete-example.yml` 파일을 열어서 주석을 꼼꼼히 읽어보세요.
이 파일에는 오늘 배운 모든 개념이 정리되어 있습니다.

```bash
# 파일 열기
nano 01-complete-example.yml
# 또는
code 01-complete-example.yml
```

**핵심 개념 체크리스트:**
- [ ] 이미지 태그 (`:latest` 절대 금지!)
- [ ] 권한 설정 (언제 `$PUID:$PGID` 사용?)
- [ ] 포트 노출 (`expose` vs `ports`)
- [ ] 볼륨 매핑 (사용자 디렉토리 vs AppData)
- [ ] CPU shares 가이드라인
- [ ] x-casaos 필수 필드

---

### Step 2: 문제 풀기 (10분)
`00-questions.md` 파일을 열어서 객관식 문제를 풉니다.

```bash
nano 00-questions.md
```

**문제 유형:**
- 공통 개념 문제 (모든 실습에 적용)
- 각 실습별 특화 문제
- 보너스 문제 (추가 학습)

**팁:**
- 확실하지 않은 문제는 `01-complete-example.yml` 참고
- 정답을 외우지 말고 *왜* 그런지 이해하기!

---

### Step 3: 실습 파일 작성 (60-90분)

#### 🔰 실습 1: qBittorrent (난이도: ⭐)
**목표**: 기본 개념 완벽 이해

```bash
nano 02-qbittorrent-exercise.yml
```

**학습 포인트:**
- 사용자 디렉토리 권한 (`$PUID:$PGID`)
- 기본적인 볼륨 매핑
- NSL Router 통합 (`expose`)
- 다국어 지원

**빈칸 개수**: 18개  
**예상 시간**: 20분

---

#### 🔸 실습 2: ConvertX (난이도: ⭐⭐)
**목표**: 특수 케이스 이해 (Root 권한)

```bash
nano 03-convertx-exercise.yml
```

**학습 포인트:**
- Root 권한이 필요한 특수 케이스 (`user: "0:0"`)
- 읽기 전용 볼륨 (`:ro`)
- 리소스 제한 (메모리)
- 보안 고려사항

**빈칸 개수**: 15개  
**예상 시간**: 20분

---

#### 🔹 실습 3: FileBrowser (난이도: ⭐⭐)
**목표**: 전체 디렉토리 접근 이해

```bash
nano 04-filebrowser-exercise.yml
```

**학습 포인트:**
- `/DATA` 전체 접근
- environment에서 PUID/PGID 설정
- 사용자 친화적 기본 계정
- Cloud 앱 카테고리

**빈칸 개수**: 12개  
**예상 시간**: 15분

---

#### 🚀 실습 4: Stirling PDF (난이도: ⭐⭐⭐ - 도전 과제!)
**목표**: 복잡한 설정 마스터

```bash
nano 05-stirling-pdf-exercise.yml
```

**학습 포인트:**
- 복잡한 환경 변수 (10개 이상)
- 다중 볼륨 매핑 (4개)
- 보안 설정 (로그인, 초기 계정)
- 고급 리소스 관리
- Healthcheck 설정

**빈칸 개수**: 16개  
**예상 시간**: 30분

---

### Step 4: 검증하기 (각 파일마다 5분)

각 파일을 작성한 후 반드시 검증하세요!

```bash
# 문법 검증 (필수!)
docker-compose -f 파일명.yml config

# 예시
docker-compose -f 02-qbittorrent-exercise.yml config
```

**출력 결과:**
- ✅ 정상: 완전한 docker-compose 설정이 출력됨
- ❌ 오류: 에러 메시지 확인 후 수정

---

### Step 5: 실제 테스트 (선택적)

**주의**: CasaOS 환경에서만 테스트하세요!

```bash
# 컨테이너 시작
docker-compose -f 파일명.yml up -d

# 로그 확인
docker-compose -f 파일명.yml logs -f

# 웹 브라우저에서 접속
# qBittorrent: http://localhost (expose한 포트에 따라)
# ConvertX: http://localhost:3000
# FileBrowser: http://localhost
# Stirling PDF: http://localhost:8080

# 테스트 완료 후 정리
docker-compose -f 파일명.yml down
```

---

## ✅ 완료 확인

### 자가 점검 체크리스트

각 실습 파일마다 다음을 확인하세요:

#### 공통 사항
- [ ] 모든 빈칸이 채워졌나요?
- [ ] 이미지 태그에 `:latest`가 없나요?
- [ ] `docker-compose config` 명령이 오류 없이 실행되나요?

#### qBittorrent
- [ ] `user: $PUID:$PGID` 설정되었나요?
- [ ] Downloads 폴더가 매핑되었나요?
- [ ] expose 포트와 webui_port가 일치하나요?

#### ConvertX
- [ ] `user: "0:0"` (Root) 설정되었나요?
- [ ] PUID=0, PGID=0 설정되었나요?
- [ ] 읽기 전용 볼륨에 `:ro`가 붙었나요?

#### FileBrowser
- [ ] `/DATA` 전체가 마운트되었나요?
- [ ] 기본 계정이 tips에 명시되었나요?

#### Stirling PDF
- [ ] 로그인이 활성화되었나요? (SECURITY_ENABLELOGIN=true)
- [ ] 4개의 볼륨이 모두 매핑되었나요?
- [ ] 메모리가 4G로 설정되었나요?

---

### 강사 확인

모든 실습을 완료했다면:

1. 🙋‍♂️ 손을 들어 강사를 호출하세요
2. 📋 강사가 각 파일을 검토합니다
3. ✅ 통과 시 조기 퇴실 가능!
4. ❌ 수정 필요 시 피드백을 받고 수정하세요

---

## 🆘 문제 해결

### 자주 하는 실수

#### 1. 이미지 태그
```yaml
# ❌ 잘못된 예
image: linuxserver/app:latest

# ✅ 올바른 예
image: linuxserver/app:5.1.2
```

#### 2. 권한 설정
```yaml
# ❌ 사용자 디렉토리 접근인데 권한 없음
volumes:
  - /DATA/Downloads:/downloads
# user 필드 없음!

# ✅ 올바른 예
user: $PUID:$PGID
volumes:
  - /DATA/Downloads:/downloads
```

#### 3. 포트 설정
```yaml
# ❌ NSL Router인데 ports 사용
ports:
  - "8080:8080"

# ✅ 올바른 예
expose:
  - 8080
```

#### 4. webui_port 불일치
```yaml
# ❌ expose와 webui_port 불일치
expose:
  - 8080
x-casaos:
  webui_port: 80  # 틀림!

# ✅ 올바른 예
expose:
  - 8080
x-casaos:
  webui_port: 8080  # 일치!
```

---

### 도움이 필요할 때

1. **01-complete-example.yml** 파일 참고
   - 모든 개념이 주석과 함께 설명되어 있습니다

2. **00-questions.md** 파일의 정답 확인
   - 각 정답에 설명이 있습니다

3. **강사에게 질문**
   - 이해가 안 되는 부분은 주저하지 말고 질문하세요!

4. **동료와 토론**
   - 함께 고민하면 더 깊이 이해할 수 있습니다

---

## 📚 추가 학습 자료

### 공식 문서
- [Docker Compose 문서](https://docs.docker.com/compose/)
- [CasaOS 문서](https://casaos.io/docs/)
- [Yundera AppStore CONTRIBUTING.md](/mnt/project/CONTRIBUTING__2_.md)
- [Yundera AppStore CLAUDE.md](/mnt/project/CLAUDE__2_.md)

### 개념 복습
- **Image 태그**: 항상 특정 버전 사용 (`:latest` 금지)
- **권한**: 사용자 디렉토리 접근 시 `$PUID:$PGID` 필수
- **포트**: NSL Router는 `expose`, 직접 접근은 `ports`
- **볼륨**: AppData는 앱 전용, 사용자 디렉토리는 공용
- **CPU shares**: 앱 특성에 맞게 10-90 사이 값 설정

---

## 🎉 마치며

Docker Compose는 처음에는 복잡해 보이지만, 
패턴을 이해하고 나면 매우 강력한 도구입니다!

오늘 배운 내용:
- ✅ Docker Compose 기본 구조
- ✅ CasaOS 특화 설정
- ✅ 실제 앱 4개 직접 작성
- ✅ 보안과 리소스 관리
- ✅ 다국어 지원 구현

이제 여러분은 실제 프로덕션 환경에서
Docker Compose 앱을 작성할 수 있습니다! 🚀

**화이팅! 💪**

---

## 📞 연락처

질문이나 피드백이 있으시면:
- 강사: 최익준 (CPO, Aptero Korea)
- Email: [이메일 주소]
- GitHub: [@사용자명]

---

**Created with ❤️ for Wonkwang University Computer Science Department**

*Docker Compose Workshop Day 2 - December 2024*
