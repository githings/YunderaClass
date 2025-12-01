# 🚀 Docker Compose 워크샵 빠른 시작 가이드

## 📦 포함된 파일들

```
docker-workshop/
├── 00-questions.md                 # 📝 객관식 문제 (61문제)
├── 01-complete-example.yml         # 📖 완전한 예제 (복습용)
├── 02-qbittorrent-exercise.yml     # 🔰 실습 1 (18개 빈칸)
├── 03-convertx-exercise.yml        # 🔸 실습 2 (15개 빈칸)
├── 04-filebrowser-exercise.yml     # 🔹 실습 3 (12개 빈칸)
├── 05-stirling-pdf-exercise.yml    # 🚀 실습 4 (16개 빈칸)
├── README.md                       # 📚 상세 안내
├── COMMIT_MESSAGE.md               # 📋 커밋 메시지 (상세)
├── GIT_COMMIT_MESSAGE.txt          # 📋 커밋 메시지 (짧은 버전)
└── QUICK_START.md                  # ⚡ 이 파일
```

## ⚡ 5분 안에 시작하기

### 학생용

1️⃣ **복습하기** (5분)
```bash
# 예제 파일 열어서 주석 읽기
nano 01-complete-example.yml
```

2️⃣ **문제 확인** (5분)
```bash
# 객관식 문제 파일 열기
nano 00-questions.md
```

3️⃣ **실습 시작** (60-90분)
```bash
# 실습 1부터 순서대로
nano 02-qbittorrent-exercise.yml
# 빈칸 채우기
# docker-compose -f 02-qbittorrent-exercise.yml config 로 검증
```

4️⃣ **완료 확인**
- 강사에게 검토 요청
- 통과 시 조기 퇴실! 🎉

---

### 강사용

#### 📋 사전 준비
```bash
# 1. 파일 배포 (USB 또는 파일 공유)
# 2. Docker 환경 확인
docker --version
docker-compose --version

# 3. CasaOS 환경 변수 확인 (필요시)
echo $PUID
echo $PGID
echo $TZ
```

#### 🎯 진행 순서
1. **도입** (10분): 오늘 학습 목표 및 진행 방식 설명
2. **복습** (15분): 01-complete-example.yml 함께 살펴보기
3. **문제 풀기** (10분): 00-questions.md 개별 학습
4. **실습 진행** (60-90분):
   - 실습 1: qBittorrent (20분)
   - 실습 2: ConvertX (20분)
   - 실습 3: FileBrowser (15분)
   - 실습 4: Stirling PDF (30분, 도전!)
5. **검증 및 피드백** (개별): 완료한 학생부터 순차적으로

#### ✅ 평가 기준
- [ ] 모든 빈칸 완성
- [ ] `docker-compose config` 통과
- [ ] 핵심 개념 이해도 확인 (구두 질문 3-5개)

---

## 🎓 학습 목표

### 기본 개념
✅ Docker Compose 파일 구조  
✅ services, volumes, environment 설정  
✅ 이미지 태그와 버전 관리  

### CasaOS 특화
✅ NSL Router 통합 (expose vs ports)  
✅ 권한 관리 (PUID/PGID)  
✅ 볼륨 매핑 전략 (/DATA 구조)  
✅ x-casaos 메타데이터 작성  

### 실전 응용
✅ 다양한 앱 유형 이해  
✅ 리소스 관리 (cpu_shares, memory)  
✅ 다국어 지원 구현  
✅ 보안 설정 (로그인, 권한)  

---

## 📊 난이도별 구성

| 실습 | 앱 이름 | 난이도 | 빈칸 | 예상 시간 | 핵심 학습 |
|------|---------|--------|------|-----------|-----------|
| 1 | qBittorrent | ⭐ | 18 | 20분 | 기본 권한, 볼륨 매핑 |
| 2 | ConvertX | ⭐⭐ | 15 | 20분 | Root 권한, 읽기 전용 |
| 3 | FileBrowser | ⭐⭐ | 12 | 15분 | 전체 디렉토리 접근 |
| 4 | Stirling PDF | ⭐⭐⭐ | 16 | 30분 | 복잡한 설정, OCR |

---

## 🔑 핵심 개념 요약

### 1. 이미지 태그
```yaml
# ❌ 절대 금지
image: app:latest

# ✅ 항상 특정 버전
image: app:1.2.3
```

### 2. 권한 설정
```yaml
# 사용자 디렉토리 접근 시
user: $PUID:$PGID

# AppData만 사용 시
# user 생략 가능 (자동 적용)

# Root 필요 시 (특수 케이스)
user: "0:0"  # + rationale.md 필수
```

### 3. 포트 노출
```yaml
# NSL Router (웹 UI)
expose:
  - 8080

# 직접 접근 (Torrent 등)
ports:
  - "6881:6881"
```

### 4. CPU Shares
```yaml
# 가이드라인
cpu_shares: 90  # 관리 도구
cpu_shares: 80  # 사용자 대면 UI
cpu_shares: 50  # 일반 앱 (기본값)
cpu_shares: 30  # 백그라운드 서비스
cpu_shares: 20  # 무거운 백그라운드
```

---

## ⚠️ 자주 하는 실수

### 실수 1: ports와 expose 혼동
```yaml
# ❌ NSL Router인데 ports 사용
ports:
  - "8080:8080"

# ✅ expose 사용
expose:
  - 8080
```

### 실수 2: webui_port 불일치
```yaml
# ❌ 불일치
expose:
  - 8080
x-casaos:
  webui_port: 80  # 틀림!

# ✅ 일치
expose:
  - 8080
x-casaos:
  webui_port: 8080
```

### 실수 3: 사용자 디렉토리 권한 누락
```yaml
# ❌ Downloads 접근인데 권한 없음
volumes:
  - /DATA/Downloads:/downloads

# ✅ 권한 추가
user: $PUID:$PGID
volumes:
  - /DATA/Downloads:/downloads
```

---

## 🆘 도움이 필요할 때

1. **01-complete-example.yml** 참고
   - 모든 개념이 주석과 함께 설명되어 있습니다

2. **00-questions.md** 정답 확인
   - 각 정답에 상세한 설명이 있습니다

3. **README.md** 상세 안내
   - 진행 방법, 문제 해결 등 전체 가이드

4. **강사에게 질문**
   - 이해가 안 되는 부분은 주저하지 말고 질문!

---

## ✅ 검증 방법

```bash
# 1. 문법 검증 (필수!)
docker-compose -f 파일명.yml config

# 2. 실제 테스트 (선택)
docker-compose -f 파일명.yml up -d

# 3. 로그 확인
docker-compose -f 파일명.yml logs -f

# 4. 종료
docker-compose -f 파일명.yml down
```

---

## 🎉 완료 후

축하합니다! 이제 여러분은:

✅ Docker Compose 앱을 직접 작성할 수 있습니다  
✅ CasaOS에 앱을 배포할 수 있습니다  
✅ 권한과 보안을 고려할 수 있습니다  
✅ 다국어 지원을 구현할 수 있습니다  

**실제 프로덕션 환경에서 사용 가능한 앱을 만들 수 있는 능력을 갖추셨습니다!** 🚀

---

## 📞 문의

- 강사: 최익준 (CPO, Aptero Korea)
- GitHub: [Worph/AppStore](https://github.com/Worph/AppStore)
- 공식 문서: [Yundera AppStore](https://github.com/Yundera/AppStore)

---

**화이팅! 💪**

*Created with ❤️ for Wonkwang University*
