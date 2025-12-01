# Docker Compose 워크샵 - 정답 요약 📝

## 🎯 강사용 정답 가이드

이 문서는 강사가 학생들의 답안을 빠르게 채점할 수 있도록 모든 정답을 정리한 문서입니다.

---

## 📦 실습 1: qBittorrent (18개 빈칸)

| 번호 | 정답 | 설명 |
|------|------|------|
| (1) | `qbittorrent` | 앱 이름 (소문자) |
| (2) | `$PUID:$PGID` | Downloads 폴더 접근 권한 |
| (3) | `lscr.io/linuxserver/qbittorrent:5.1.2` | LinuxServer.io 이미지, 버전 5.1.2 |
| (4) | `expose` | NSL Router 사용 시 expose |
| (5) | `80` | 웹 UI 포트 |
| (6) | `80` | WEBUI_PORT 환경 변수 |
| (7) | `/DATA/AppData/qbittorrent/config` | 설정 디렉토리 |
| (8) | `/DATA/Downloads` | 다운로드 디렉토리 |
| (9) | `20` | CPU shares (무거운 백그라운드) |
| (10) | `qbittorrent` | 메인 서비스 이름 |
| (11) | `80` | webui_port (expose와 일치) |
| (12) | `amd64` | 지원 아키텍처 1 |
| (13) | `arm64` | 지원 아키텍처 2 |
| (14) | `Downloader` | 카테고리 |
| (15) | `https://cdn.jsdelivr.net/gh/Yundera/AppStore@main/Apps/qBittorrent/icon.png` | 아이콘 URL |
| (16) | `qBittorrent` | 앱 제목 (공식 표기) |
| (17) | `qbittorrent` | store_app_id (name과 동일) |
| (18) | `false` | is_uncontrolled |

---

## 🔄 실습 2: ConvertX (15개 빈칸)

| 번호 | 정답 | 설명 |
|------|------|------|
| (1) | `convertx` | 앱 이름 (소문자) |
| (2) | `ghcr.io/c4illin/convertx:v0.14.1` | GitHub Container Registry 이미지 |
| (3) | `0:0` | Root 권한 (SQLite 권한 문제) |
| (4) | `2G` | 메모리 제한 (파일 변환용) |
| (5) | `expose` | NSL Router 사용 |
| (6) | `3000` | 웹 UI 포트 |
| (7) | `0` | PUID (root) |
| (8) | `0` | PGID (root) |
| (9) | `ro` | 읽기 전용 마운트 (Downloads) |
| (10) | `ro` | 읽기 전용 마운트 (Documents) |
| (11) | `Utilities` | 카테고리 |
| (12) | `3000` | webui_port |
| (13) | `convertx` | store_app_id |
| (14) | `false` | is_uncontrolled |

---

## 📁 실습 3: FileBrowser (12개 빈칸)

| 번호 | 정답 | 설명 |
|------|------|------|
| (1) | `filebrowser` | 앱 이름 (소문자) |
| (2) | `filebrowser/filebrowser:v2.23.0` | 공식 이미지, 버전 v2.23.0 |
| (3) | `bridge` | 네트워크 모드 |
| (4) | `# user: $PUID:$PGID` 또는 생략 | user 필드 (주석 처리 또는 생략) |
| (5) | `80` | 웹 UI 포트 |
| (6) | `/DATA` | FileBrowser 관리 디렉토리 |
| (7) | `80` | CPU shares (사용자 대면 UI) |
| (8) | `filebrowser` | 메인 서비스 이름 |
| (9) | `Cloud` | 카테고리 (파일 관리) |
| (10) | `80` | webui_port |
| (11) | `filebrowser` | store_app_id |
| (12) | `false` | is_uncontrolled |

---

## 📄 실습 4: Stirling PDF (16개 빈칸)

| 번호 | 정답 | 설명 |
|------|------|------|
| (1) | `stirlingtools/stirling-pdf:2.0.0` | stirlingtools 이미지, 버전 2.0.0 |
| (2) | `$PUID:$PGID` | Documents 접근 권한 |
| (3) | `4G` | 메모리 제한 (PDF 처리용) |
| (4) | `8080` | 웹 UI 포트 |
| (5) | `true` | 로그인 활성화 (보안) |
| (6) | `en_US` | 기본 언어 |
| (7) | `ro` | 읽기 전용 (Documents) |
| (8) | `ro` | 읽기 전용 (Downloads) |
| (9) | `70` | CPU shares (무거운 인터랙티브) |
| (10) | `stirling-pdf` | 메인 서비스 이름 |
| (11) | `Utilities` | 카테고리 |
| (12) | `8080` | webui_port |
| (13) | `stirling-pdf` | store_app_id |
| (14) | `false` | is_uncontrolled |

---

## ✅ 채점 기준

### 필수 체크 사항

#### 모든 실습 공통
- [ ] 모든 빈칸이 채워졌는가?
- [ ] 이미지 태그에 `:latest`가 없는가?
- [ ] `docker-compose config` 명령이 오류 없이 실행되는가?

#### 실습 1 (qBittorrent)
- [ ] `user: $PUID:$PGID` 설정되었는가?
- [ ] Downloads 폴더가 올바르게 매핑되었는가?
- [ ] expose 포트와 webui_port가 일치하는가?

#### 실습 2 (ConvertX)
- [ ] `user: "0:0"` (Root) 설정되었는가?
- [ ] PUID=0, PGID=0 설정되었는가?
- [ ] 읽기 전용 볼륨에 `:ro`가 붙었는가?

#### 실습 3 (FileBrowser)
- [ ] `/DATA` 전체가 마운트되었는가?
- [ ] environment에 PUID/PGID가 설정되었는가?

#### 실습 4 (Stirling PDF)
- [ ] 로그인이 활성화되었는가? (SECURITY_ENABLELOGIN=true)
- [ ] 4개의 볼륨이 모두 올바르게 매핑되었는가?
- [ ] 메모리가 4G로 설정되었는가?

---

## 📊 채점 시트

### 학생 이름: __________________

| 실습 | 빈칸 개수 | 정답 개수 | 점수 | 비고 |
|------|-----------|-----------|------|------|
| 1. qBittorrent | 18 | ____ / 18 | ____% | |
| 2. ConvertX | 15 | ____ / 15 | ____% | |
| 3. FileBrowser | 12 | ____ / 12 | ____% | |
| 4. Stirling PDF | 16 | ____ / 16 | ____% | |
| **총계** | **61** | **____ / 61** | **____%** | |

### 개념 이해도 확인 (구두 질문)

1. **권한 관리**: "언제 `user: $PUID:$PGID`를 사용해야 하나요?"
   - [ ] 정확히 설명함
   - [ ] 부분적으로 이해함
   - [ ] 이해 부족

2. **NSL Router**: "expose와 ports의 차이는 무엇인가요?"
   - [ ] 정확히 설명함
   - [ ] 부분적으로 이해함
   - [ ] 이해 부족

3. **CPU Shares**: "앱 유형에 따라 cpu_shares 값을 어떻게 정하나요?"
   - [ ] 정확히 설명함
   - [ ] 부분적으로 이해함
   - [ ] 이해 부족

### 최종 평가
- [ ] **통과** - 조기 퇴실 가능
- [ ] **재검토 필요** - 수정 후 재제출
- [ ] **개념 보충 필요** - 추가 설명 필요

---

## 🎯 자주 틀리는 부분

### 1. 이미지 태그
```yaml
# ❌ 흔한 실수
image: app:latest

# ✅ 정답
image: app:1.2.3
```

### 2. 포트 설정
```yaml
# ❌ NSL Router인데 ports 사용
ports:
  - "8080:8080"

# ✅ expose 사용
expose:
  - 8080
```

### 3. webui_port 불일치
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

### 4. 권한 누락
```yaml
# ❌ Downloads 접근인데 권한 없음
volumes:
  - /DATA/Downloads:/downloads
# user 필드 없음!

# ✅ 권한 추가
user: $PUID:$PGID
volumes:
  - /DATA/Downloads:/downloads
```

---

## 📞 문의 사항

채점 중 불명확한 부분이 있거나, 학생이 독특한 접근 방식을 사용한 경우:

1. **완성된 파일 검증**
   ```bash
   docker-compose -f 파일명.yml config
   ```

2. **답안 파일 확인**
   - `ANSWERS/` 폴더의 정답 파일 참고

3. **개념 설명**
   - `01-complete-example.yml`의 주석 활용

4. **가이드 문서**
   - `README.md`: 종합 안내
   - `QUICK_START.md`: 빠른 참고

---

## 💡 추가 학습 자료

학생이 특정 개념을 어려워할 때 참고할 수 있는 자료:

1. **권한 관리**
   - CONTRIBUTING.md의 "Permission Strategy" 섹션
   - 01-complete-example.yml의 2-4번 섹션

2. **NSL Router**
   - CONTRIBUTING.md의 "NSL Router Integration" 섹션
   - CLAUDE.md의 관련 내용

3. **볼륨 구조**
   - CONTRIBUTING.md의 "File Structure" 섹션
   - 01-complete-example.yml의 2-7번 섹션

4. **CPU Shares**
   - CONTRIBUTING.md의 "CPU Share Guidelines" 섹션

---

**채점 화이팅! 💪**

*학생들이 실력을 키울 수 있도록 건설적인 피드백을 부탁드립니다!*
