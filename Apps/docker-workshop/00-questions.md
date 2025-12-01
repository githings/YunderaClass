# Docker Compose 워크샵 - 객관식 문제 📝

이 문서에는 실습 파일의 빈칸을 채우기 위한 객관식 문제들이 있습니다.
각 문제를 신중히 읽고 정답을 선택한 후, 해당하는 실습 파일의 빈칸에 입력하세요!

---

## 📌 공통 개념 문제

### Q0-1. Docker Compose에서 이미지 태그를 지정할 때 올바른 방법은?
a) `image: linuxserver/app:latest`  
b) `image: linuxserver/app:5.1.2`  
c) `image: linuxserver/app`  
d) `image: linuxserver/app:stable`

**정답: b)**
- CONTRIBUTING.md 규칙: 절대 :latest 사용 금지!
- 특정 버전 태그 필수 (예: 5.1.2, v2.0.0 등)

---

### Q0-2. 사용자 디렉토리(/DATA/Documents, /DATA/Downloads)에 접근하는 앱의 권한 설정은?
a) `user: root`  
b) `user: $PUID:$PGID`  
c) `user: 0:0`  
d) user 필드 생략

**정답: b)**
- 사용자 디렉토리 접근 시 반드시 $PUID:$PGID 사용
- CasaOS 시스템 변수로 동적으로 권한 설정

---

### Q0-3. NSL Router를 사용할 때 웹 UI 포트를 노출하는 올바른 방법은?
a) `ports: - "8080:8080"`  
b) `expose: - 8080`  
c) `publish: - 8080`  
d) `bind: - 8080`

**정답: b)**
- NSL Router 통합 시 expose 사용 (내부 네트워크만 노출)
- ports는 직접 접근이 필요한 특별한 경우만 사용

---

## 📦 실습 1: qBittorrent

### Q1-1. qBittorrent 앱의 name은?
a) `qbittorrent`  
b) `qBittorrent`  
c) `QBittorrent`  
d) `qb-torrent`

**정답: a)**
- name은 소문자, 숫자, 하이픈, 언더스코어만 사용
- qbittorrent (모두 소문자)

---

### Q1-2. qBittorrent는 /DATA/Downloads에 접근합니다. 올바른 user 설정은?
a) `user: root`  
b) `user: $PUID:$PGID`  
c) `user: 0:0`  
d) user 필드 생략

**정답: b)**
- Downloads 폴더는 사용자 디렉토리
- 반드시 $PUID:$PGID 사용

---

### Q1-3. qBittorrent에서 사용하는 LinuxServer.io 이미지와 버전은?
a) `lscr.io/linuxserver/qbittorrent:latest`  
b) `linuxserver/qbittorrent:5.1.2`  
c) `lscr.io/linuxserver/qbittorrent:5.1.2`  
d) `ghcr.io/linuxserver/qbittorrent:5.1.2`

**정답: c)**
- LinuxServer.io 레지스트리: lscr.io
- 특정 버전: 5.1.2

---

### Q1-4. 웹 UI를 내부 네트워크에만 노출하는 키워드는?
a) `ports`  
b) `expose`  
c) `publish`  
d) `network`

**정답: b)**
- NSL Router 사용 시 expose 키워드 사용

---

### Q1-5. qBittorrent 웹 UI 포트는?
a) `8080`  
b) `8081`  
c) `80`  
d) `443`

**정답: c)**
- qBittorrent는 포트 80 사용 (WEBUI_PORT=80)

---

### Q1-6. WEBUI_PORT 환경 변수 값은?
a) `8080`  
b) `443`  
c) `80`  
d) `6881`

**정답: c)**
- 웹 UI 포트와 일치: 80

---

### Q1-7. qBittorrent 설정 파일이 저장될 볼륨 경로는?
a) `/DATA/AppData/qbittorrent/config`  
b) `/DATA/AppData/qBittorrent/config`  
c) `/DATA/AppData/$AppID/config`  
d) `/DATA/qbittorrent/config`

**정답: a) 또는 c)** (둘 다 맞음)
- $AppID는 앱 이름(qbittorrent)으로 치환됨
- 경로: /DATA/AppData/qbittorrent/config

---

### Q1-8. 다운로드 파일이 저장될 볼륨 경로는?
a) `/DATA/downloads`  
b) `/DATA/Downloads`  
c) `/DATA/Download`  
d) `/DATA/AppData/qbittorrent/downloads`

**정답: b)**
- 대소문자 구분: Downloads (D 대문자)
- 사용자 공용 다운로드 폴더

---

### Q1-9. qBittorrent의 cpu_shares 값은? (백그라운드 다운로드 서비스)
a) `10`  
b) `20`  
c) `30`  
d) `50`

**정답: b)**
- 가이드: 20 = 무거운 백그라운드 처리
- Torrent 다운로드는 백그라운드 작업

---

### Q1-10. x-casaos 섹션의 main 값은?
a) `qbittorrent-service`  
b) `qbittorrent`  
c) `qBittorrent`  
d) `torrent`

**정답: b)**
- services 아래의 서비스 이름과 일치: qbittorrent

---

### Q1-11. webui_port 값은?
a) `8080`  
b) `6881`  
c) `80`  
d) `443`

**정답: c)**
- expose한 포트와 일치: 80

---

### Q1-12~13. qBittorrent가 지원하는 아키텍처 2개는?
a) `amd64`  
b) `arm64`  
c) `arm`  
d) `x86`

**정답: a), b)**
- LinuxServer.io 이미지는 amd64와 arm64 지원

---

### Q1-14. qBittorrent의 카테고리는?
a) `Backup`  
b) `Cloud`  
c) `Downloader`  
d) `Media`

**정답: c)**
- 다운로드 관련 앱: Downloader 카테고리

---

### Q1-15. icon URL의 올바른 형식은?
a) `https://cdn.jsdelivr.net/gh/Worph/AppStore@main/Apps/qBittorrent/icon.png`  
b) `https://cdn.jsdelivr.net/gh/Yundera/AppStore@main/Apps/qBittorrent/icon.png`  
c) `https://github.com/Yundera/AppStore/blob/main/Apps/qBittorrent/icon.png`  
d) `https://raw.githubusercontent.com/Yundera/AppStore/main/Apps/qBittorrent/icon.png`

**정답: b)**
- Yundera 레포지토리 사용 (fork가 아닌 메인)
- jsdelivr CDN 사용

---

### Q1-16. title.en_us 값은?
a) `qbittorrent`  
b) `qBittorrent`  
c) `QBittorrent`  
d) `Qbittorrent`

**정답: b)**
- 공식 표기: qBittorrent (q와 B 대문자)

---

### Q1-17. store_app_id 값은?
a) `qBittorrent`  
b) `qbittorrent`  
c) `qb-torrent`  
d) `torrent`

**정답: b)**
- name 값과 동일: qbittorrent (소문자)

---

### Q1-18. is_uncontrolled 값은?
a) `true`  
b) `false`  
c) `yes`  
d) `no`

**정답: b)**
- CasaOS가 관리하는 일반 앱: false

---

## 🔄 실습 2: ConvertX

### Q2-1. ConvertX 앱의 name은?
a) `ConvertX`  
b) `convertx`  
c) `convert-x`  
d) `convertX`

**정답: b)**
- 소문자: convertx

---

### Q2-2. ConvertX 이미지는? (GitHub Container Registry, v0.14.1)
a) `ghcr.io/c4illin/convertx:latest`  
b) `ghcr.io/c4illin/convertx:v0.14.1`  
c) `c4illin/convertx:v0.14.1`  
d) `docker.io/c4illin/convertx:v0.14.1`

**정답: b)**
- GitHub Container Registry: ghcr.io
- 작성자: c4illin
- 버전: v0.14.1

---

### Q2-3. ConvertX의 특수한 user 설정은? (SQLite 권한 문제)
a) `$PUID:$PGID`  
b) `1000:1000`  
c) `0:0`  
d) user 필드 생략

**정답: c)**
- 특수 케이스: root 필요 (0:0)
- 이유: SQLite 데이터베이스 권한 문제
- rationale.md에 문서화 필요

---

### Q2-4. ConvertX의 메모리 제한은? (파일 변환용)
a) `512M`  
b) `1G`  
c) `2G`  
d) `4G`

**정답: c)**
- 파일 변환은 메모리 사용량이 높음
- 권장: 2G

---

### Q2-5. 웹 UI 포트 노출 키워드는?
a) `ports`  
b) `expose`  
c) `publish`  
d) `bind`

**정답: b)**
- NSL Router 사용: expose

---

### Q2-6. ConvertX 웹 UI 포트는?
a) `80`  
b) `8080`  
c) `3000`  
d) `443`

**정답: c)**
- ConvertX는 3000 포트 사용

---

### Q2-7~8. Root로 실행하므로 PUID와 PGID 값은?
a) `1000`  
b) `$PUID`  
c) `$PGID`  
d) `0`

**정답: d), d)**
- Root 실행 시: PUID=0, PGID=0

---

### Q2-9~10. Downloads와 Documents 볼륨의 마운트 옵션은? (읽기 전용)
a) `rw`  
b) `ro`  
c) `read-only`  
d) `r`

**정답: b)**
- 읽기 전용 마운트: :ro
- 변환할 파일만 읽고, 쓰기 불가

---

### Q2-11. ConvertX의 카테고리는?
a) `Backup`  
b) `Cloud`  
c) `Utilities`  
d) `Media`

**정답: c)**
- 유틸리티 도구: Utilities

---

### Q2-12. webui_port 값은?
a) `80`  
b) `8080`  
c) `3000`  
d) `443`

**정답: c)**
- expose한 포트와 일치: 3000

---

### Q2-13. store_app_id 값은?
a) `ConvertX`  
b) `convertx`  
c) `convert-x`  
d) `convertX`

**정답: b)**
- name과 동일: convertx

---

### Q2-14. is_uncontrolled 값은?
a) `true`  
b) `false`

**정답: b)**
- 일반 관리 앱: false

---

## 📁 실습 3: FileBrowser

### Q3-1. FileBrowser 앱의 name은?
a) `FileBrowser`  
b) `filebrowser`  
c) `file-browser`  
d) `fileBrowser`

**정답: b)**
- 소문자: filebrowser

---

### Q3-2. FileBrowser 이미지는? (v2.23.0)
a) `filebrowser/filebrowser:latest`  
b) `filebrowser/filebrowser:v2.23.0`  
c) `linuxserver/filebrowser:v2.23.0`  
d) `ghcr.io/filebrowser/filebrowser:v2.23.0`

**정답: b)**
- 공식 이미지: filebrowser/filebrowser
- 버전: v2.23.0

---

### Q3-3. network_mode 값은?
a) `host`  
b) `bridge`  
c) `none`  
d) `container`

**정답: b)**
- 기본 브릿지 네트워크: bridge

---

### Q3-4. FileBrowser는 environment에서 PUID/PGID를 설정합니다. user 필드는?
a) `user: $PUID:$PGID` (활성화)  
b) `# user: $PUID:$PGID` (주석 처리)  
c) `user: 0:0`  
d) user 필드 없음

**정답: b) 또는 d)**
- FileBrowser는 environment로 권한 처리
- user 필드는 주석 처리되거나 없음

---

### Q3-5. FileBrowser 웹 UI 포트는?
a) `8080`  
b) `443`  
c) `80`  
d) `3000`

**정답: c)**
- FileBrowser는 80 포트 사용

---

### Q3-6. FileBrowser가 관리할 전체 디렉토리는?
a) `/DATA`  
b) `/DATA/Documents`  
c) `/DATA/Downloads`  
d) `/DATA/AppData`

**정답: a)**
- /DATA 전체를 /srv로 마운트
- 모든 사용자 디렉토리 접근 가능

---

### Q3-7. FileBrowser의 cpu_shares 값은? (파일 관리 UI)
a) `50`  
b) `70`  
c) `80`  
d) `90`

**정답: c)**
- 가이드: 80 = 사용자 대면 인터랙티브

---

### Q3-8. main 값은?
a) `filebrowser-service`  
b) `filebrowser`  
c) `FileBrowser`  
d) `file-browser`

**정답: b)**
- services 아래의 서비스 이름: filebrowser

---

### Q3-9. FileBrowser의 카테고리는?
a) `Backup`  
b) `Cloud`  
c) `Utilities`  
d) `Media`

**정답: b)**
- 파일 관리는 Cloud 카테고리

---

### Q3-10. webui_port 값은?
a) `8080`  
b) `443`  
c) `80`  
d) `3000`

**정답: c)**
- expose한 포트와 일치: 80

---

### Q3-11. store_app_id 값은?
a) `FileBrowser`  
b) `filebrowser`  
c) `file-browser`  
d) `fileBrowser`

**정답: b)**
- name과 동일: filebrowser (소문자)

---

### Q3-12. is_uncontrolled 값은?
a) `true`  
b) `false`

**정답: b)**
- 일반 관리 앱: false

---

## 📄 실습 4: Stirling PDF (도전 과제!)

### Q4-1. Stirling PDF 이미지는? (v2.0.0)
a) `stirlingtools/stirling-pdf:latest`  
b) `stirlingtools/stirling-pdf:v2.0.0`  
c) `stirlingtools/stirling-pdf:2.0.0`  
d) `frooodle/s-pdf:2.0.0`

**정답: c)**
- stirlingtools 레지스트리 사용 (frooodle에서 이동)
- 버전: 2.0.0 (v 접두사 없음)

---

### Q4-2. Stirling PDF의 user 설정은? (Documents 접근)
a) `user: root`  
b) `user: $PUID:$PGID`  
c) `user: 0:0`  
d) user 필드 생략

**정답: b)**
- Documents 폴더 접근 필요
- $PUID:$PGID 사용

---

### Q4-3. PDF 처리를 위한 메모리 제한은?
a) `512M`  
b) `1G`  
c) `2G`  
d) `4G`

**정답: d)**
- PDF 처리는 메모리 많이 사용
- 권장: 4G

---

### Q4-4. Stirling PDF 웹 UI 포트는?
a) `80`  
b) `3000`  
c) `8080`  
d) `443`

**정답: c)**
- Stirling PDF는 8080 포트 사용

---

### Q4-5. 로그인 기능 활성화 환경 변수 값은? (보안 권장)
a) `true`  
b) `false`  
c) `yes`  
d) `no`

**정답: a)**
- 보안을 위해 로그인 활성화 권장: true

---

### Q4-6. 기본 언어 설정 환경 변수 값은?
a) `ko_KR`  
b) `en_US`  
c) `zh_CN`  
d) `ja_JP`

**정답: b)**
- 영어를 기본으로: en_US

---

### Q4-7~8. Documents와 Downloads 볼륨의 마운트 옵션은? (읽기 전용)
a) `rw`  
b) `ro`  
c) `read-only`  
d) `r`

**정답: b)**
- 읽기 전용: :ro
- PDF 원본 파일만 읽고, 직접 수정 불가

---

### Q4-9. Stirling PDF의 cpu_shares 값은? (PDF 편집)
a) `50`  
b) `70`  
c) `80`  
d) `90`

**정답: b)**
- 가이드: 70 = 무거운 작업이 있는 인터랙티브
- PDF 처리는 CPU를 많이 사용

---

### Q4-10. main 값은?
a) `stirling`  
b) `stirling-pdf`  
c) `stirlingpdf`  
d) `pdf`

**정답: b)**
- services 아래의 서비스 이름: stirling-pdf

---

### Q4-11. Stirling PDF의 카테고리는?
a) `Backup`  
b) `Cloud`  
c) `Utilities`  
d) `Media`

**정답: c)**
- PDF 편집 도구: Utilities

---

### Q4-12. webui_port 값은?
a) `80`  
b) `3000`  
c) `8080`  
d) `443`

**정답: c)**
- expose한 포트와 일치: 8080

---

### Q4-13. store_app_id 값은?
a) `stirlingpdf`  
b) `stirling-pdf`  
c) `Stirling-PDF`  
d) `stirling_pdf`

**정답: b)**
- name과 동일: stirling-pdf (하이픈 포함)

---

### Q4-14. is_uncontrolled 값은?
a) `true`  
b) `false`

**정답: b)**
- 일반 관리 앱: false

---

## 🎯 보너스 질문

### QB-1. CasaOS에서 $AppID 변수는 무엇을 의미하나요?
a) 컨테이너 ID  
b) 앱 이름 (name 값)  
c) 사용자 ID  
d) 포트 번호

**정답: b)**
- $AppID = 앱 이름 (docker-compose.yml의 name 값)

---

### QB-2. NSL Router를 사용할 때 생성되는 도메인 패턴은?
a) `https://username.nsl.sh/appname`  
b) `https://appname.nsl.sh`  
c) `https://appname-username.nsl.sh`  
d) `https://nsl.sh/appname-username`

**정답: c)**
- 패턴: https://appname-username.nsl.sh
- 포트 80이 아닌 경우: https://포트-appname-username.nsl.sh

---

### QB-3. CasaOS 시스템 변수가 아닌 것은?
a) `$PUID`  
b) `$PGID`  
c) `$TZ`  
d) `$USERNAME`

**정답: d)**
- 시스템 변수: $PUID, $PGID, $TZ, $default_pwd, $AppID
- $USERNAME은 시스템 변수가 아님

---

### QB-4. rationale.md 파일이 필요한 경우는?
a) 앱이 root 권한이 필요할 때  
b) 앱이 port 80을 사용할 때  
c) 앱이 다국어를 지원할 때  
d) 앱이 CPU shares를 사용할 때

**정답: a)**
- root 권한 필요 시 이유를 rationale.md에 문서화

---

### QB-5. pre-install-cmd를 사용할 때 지켜야 할 보안 규칙이 아닌 것은?
a) 특정 버전 태그 사용 (:latest 금지)  
b) 사용자 디렉토리 작업 시 --user $PUID:$PGID 사용  
c) 반드시 Alpine Linux 사용  
d) 여러 번 실행해도 안전하도록 작성 (멱등성)

**정답: c)**
- Alpine Linux 사용은 필수가 아님
- 다른 것들은 모두 보안 규칙

---

## 🏆 완료 확인

모든 문제를 풀고 실습 파일의 빈칸을 채웠다면:

1. ✅ 각 docker-compose 파일의 문법 검증
   ```bash
   docker-compose -f 파일명.yml config
   ```

2. ✅ 실제 테스트 (선택적)
   ```bash
   docker-compose -f 파일명.yml up -d
   ```

3. ✅ 웹 브라우저에서 접속 확인
   - qBittorrent: http://localhost (포트 설정에 따라 다름)
   - ConvertX: http://localhost:3000
   - FileBrowser: http://localhost
   - Stirling PDF: http://localhost:8080

4. ✅ 완료 후 강사에게 확인 받기!

---

## 💡 학습 팁

- 막히는 문제가 있으면 01-complete-example.yml 파일을 참고하세요
- CONTRIBUTING.md와 CLAUDE.md 파일도 도움이 됩니다
- 정답을 찾는 것보다 *왜* 그런지 이해하는 것이 중요합니다!

**화이팅! 🚀**
