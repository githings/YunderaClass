# Docker Compose 워크샵 - 객관식 문제 📝

이 문서에는 실습 파일의 빈칸을 채우기 위한 객관식 문제들이 있습니다.
각 문제를 신중히 읽고 정답을 선택한 후, 해당하는 실습 파일의 빈칸에 입력하세요!

**💡 힌트**: 막히는 문제가 있으면 `01-complete-example.yml` 파일을 참고하세요!

---

## 📌 공통 개념 문제

### Q0-1. Docker Compose에서 이미지 태그를 지정할 때 올바른 방법은?
a) `image: linuxserver/app:latest`  
b) `image: linuxserver/app:5.1.2`  
c) `image: linuxserver/app`  
d) `image: linuxserver/app:stable`

**정답: ______**

---

### Q0-2. 사용자 디렉토리(/DATA/Documents, /DATA/Downloads)에 접근하는 앱의 권한 설정은?
a) `user: root`  
b) `user: $PUID:$PGID`  
c) `user: 0:0`  
d) user 필드 생략

**정답: ______**

---

### Q0-3. NSL Router를 사용할 때 웹 UI 포트를 노출하는 올바른 방법은?
a) `ports: - "8080:8080"`  
b) `expose: - 8080`  
c) `publish: - 8080`  
d) `bind: - 8080`

**정답: ______**

---

## 📦 실습 1: qBittorrent

### Q1-1. qBittorrent 앱의 name은?
a) `qbittorrent`  
b) `qBittorrent`  
c) `QBittorrent`  
d) `qb-torrent`

**정답: ______**

---

### Q1-2. qBittorrent는 /DATA/Downloads에 접근합니다. 올바른 user 설정은?
a) `user: root`  
b) `user: $PUID:$PGID`  
c) `user: 0:0`  
d) user 필드 생략

**정답: ______**

---

### Q1-3. qBittorrent에서 사용하는 LinuxServer.io 이미지와 버전은?
a) `lscr.io/linuxserver/qbittorrent:latest`  
b) `linuxserver/qbittorrent:5.1.2`  
c) `lscr.io/linuxserver/qbittorrent:5.1.2`  
d) `ghcr.io/linuxserver/qbittorrent:5.1.2`

**정답: ______**

---

### Q1-4. 웹 UI를 내부 네트워크에만 노출하는 키워드는?
a) `ports`  
b) `expose`  
c) `publish`  
d) `network`

**정답: ______**

---

### Q1-5. qBittorrent 웹 UI 포트는?
a) `8080`  
b) `8081`  
c) `80`  
d) `443`

**정답: ______**

---

### Q1-6. WEBUI_PORT 환경 변수 값은?
a) `8080`  
b) `443`  
c) `80`  
d) `6881`

**정답: ______**

---

### Q1-7. qBittorrent 설정 파일이 저장될 볼륨 경로는?
a) `/DATA/AppData/qbittorrent/config`  
b) `/DATA/AppData/qBittorrent/config`  
c) `/DATA/AppData/$AppID/config`  
d) `/DATA/qbittorrent/config`

**정답: ______** (a 또는 c 둘 다 정답)

---

### Q1-8. 다운로드 파일이 저장될 볼륨 경로는?
a) `/DATA/downloads`  
b) `/DATA/Downloads`  
c) `/DATA/Download`  
d) `/DATA/AppData/qbittorrent/downloads`

**정답: ______**

---

### Q1-9. qBittorrent의 cpu_shares 값은? (백그라운드 다운로드 서비스)
a) `10`  
b) `20`  
c) `30`  
d) `50`

**정답: ______**

---

### Q1-10. x-casaos 섹션의 main 값은?
a) `qbittorrent-service`  
b) `qbittorrent`  
c) `qBittorrent`  
d) `torrent`

**정답: ______**

---

### Q1-11. webui_port 값은?
a) `8080`  
b) `6881`  
c) `80`  
d) `443`

**정답: ______**

---

### Q1-12~13. qBittorrent가 지원하는 아키텍처 2개는?
a) `amd64`  
b) `arm64`  
c) `arm`  
d) `x86`

**정답: ______, ______**

---

### Q1-14. qBittorrent의 카테고리는?
a) `Backup`  
b) `Cloud`  
c) `Downloader`  
d) `Media`

**정답: ______**

---

### Q1-15. icon URL은 어느 레포지토리를 사용하나요?
a) `Worph/AppStore`  
b) `Yundera/AppStore`  
c) `IceWhaleTech/CasaOS-AppStore`  
d) `BookJJun-IJ/AppStore`

**정답: ______**

---

### Q1-16. title.en_us 값은?
a) `qbittorrent`  
b) `qBittorrent`  
c) `QBittorrent`  
d) `Qbittorrent`

**정답: ______**

---

### Q1-17. store_app_id 값은?
a) `qBittorrent`  
b) `qbittorrent`  
c) `qb-torrent`  
d) `torrent`

**정답: ______**

---

### Q1-18. is_uncontrolled 값은?
a) `true`  
b) `false`  
c) `yes`  
d) `no`

**정답: ______**

---

## 🔄 실습 2: ConvertX

### Q2-1. ConvertX 앱의 name은?
a) `ConvertX`  
b) `convertx`  
c) `convert-x`  
d) `convertX`

**정답: ______**

---

### Q2-2. ConvertX 이미지는? (GitHub Container Registry, v0.14.1)
a) `ghcr.io/c4illin/convertx:latest`  
b) `ghcr.io/c4illin/convertx:v0.14.1`  
c) `c4illin/convertx:v0.14.1`  
d) `docker.io/c4illin/convertx:v0.14.1`

**정답: ______**

---

### Q2-3. ConvertX의 특수한 user 설정은? (SQLite 권한 문제)
a) `$PUID:$PGID`  
b) `1000:1000`  
c) `0:0`  
d) user 필드 생략

**정답: ______**

---

### Q2-4. ConvertX의 메모리 제한은? (파일 변환용)
a) `512M`  
b) `1G`  
c) `2G`  
d) `4G`

**정답: ______**

---

### Q2-5. 웹 UI 포트 노출 키워드는?
a) `ports`  
b) `expose`  
c) `publish`  
d) `bind`

**정답: ______**

---

### Q2-6. ConvertX 웹 UI 포트는?
a) `80`  
b) `8080`  
c) `3000`  
d) `443`

**정답: ______**

---

### Q2-7~8. Root로 실행하므로 PUID와 PGID 값은?
a) `1000`  
b) `$PUID`  
c) `$PGID`  
d) `0`

**정답: ______, ______**

---

### Q2-9~10. Downloads와 Documents 볼륨의 마운트 옵션은? (읽기 전용)
a) `rw`  
b) `ro`  
c) `read-only`  
d) `r`

**정답: ______, ______**

---

### Q2-11. ConvertX의 카테고리는?
a) `Backup`  
b) `Cloud`  
c) `Utilities`  
d) `Media`

**정답: ______**

---

### Q2-12. webui_port 값은?
a) `80`  
b) `8080`  
c) `3000`  
d) `443`

**정답: ______**

---

### Q2-13. store_app_id 값은?
a) `ConvertX`  
b) `convertx`  
c) `convert-x`  
d) `convertX`

**정답: ______**

---

### Q2-14. is_uncontrolled 값은?
a) `true`  
b) `false`

**정답: ______**

---

## 📁 실습 3: FileBrowser

### Q3-1. FileBrowser 앱의 name은?
a) `FileBrowser`  
b) `filebrowser`  
c) `file-browser`  
d) `fileBrowser`

**정답: ______**

---

### Q3-2. FileBrowser 이미지는? (v2.23.0)
a) `filebrowser/filebrowser:latest`  
b) `filebrowser/filebrowser:v2.23.0`  
c) `linuxserver/filebrowser:v2.23.0`  
d) `ghcr.io/filebrowser/filebrowser:v2.23.0`

**정답: ______**

---

### Q3-3. network_mode 값은?
a) `host`  
b) `bridge`  
c) `none`  
d) `container`

**정답: ______**

---

### Q3-4. FileBrowser는 environment에서 PUID/PGID를 설정합니다. user 필드는?
a) `user: $PUID:$PGID` (활성화)  
b) 주석 처리 또는 생략  
c) `user: 0:0`  
d) `user: 1000:1000`

**정답: ______**

---

### Q3-5. FileBrowser 웹 UI 포트는?
a) `8080`  
b) `443`  
c) `80`  
d) `3000`

**정답: ______**

---

### Q3-6. FileBrowser가 관리할 전체 디렉토리는?
a) `/DATA`  
b) `/DATA/Documents`  
c) `/DATA/Downloads`  
d) `/DATA/AppData`

**정답: ______**

---

### Q3-7. FileBrowser의 cpu_shares 값은? (파일 관리 UI)
a) `50`  
b) `70`  
c) `80`  
d) `90`

**정답: ______**

---

### Q3-8. main 값은?
a) `filebrowser-service`  
b) `filebrowser`  
c) `FileBrowser`  
d) `file-browser`

**정답: ______**

---

### Q3-9. FileBrowser의 카테고리는?
a) `Backup`  
b) `Cloud`  
c) `Utilities`  
d) `Media`

**정답: ______**

---

### Q3-10. webui_port 값은?
a) `8080`  
b) `443`  
c) `80`  
d) `3000`

**정답: ______**

---

### Q3-11. store_app_id 값은?
a) `FileBrowser`  
b) `filebrowser`  
c) `file-browser`  
d) `fileBrowser`

**정답: ______**

---

### Q3-12. is_uncontrolled 값은?
a) `true`  
b) `false`

**정답: ______**

---

## 📄 실습 4: Stirling PDF (도전 과제!)

### Q4-1. Stirling PDF 이미지는? (v2.0.0)
a) `stirlingtools/stirling-pdf:latest`  
b) `stirlingtools/stirling-pdf:v2.0.0`  
c) `stirlingtools/stirling-pdf:2.0.0`  
d) `frooodle/s-pdf:2.0.0`

**정답: ______**

---

### Q4-2. Stirling PDF의 user 설정은? (Documents 접근)
a) `user: root`  
b) `user: $PUID:$PGID`  
c) `user: 0:0`  
d) user 필드 생략

**정답: ______**

---

### Q4-3. PDF 처리를 위한 메모리 제한은?
a) `512M`  
b) `1G`  
c) `2G`  
d) `4G`

**정답: ______**

---

### Q4-4. Stirling PDF 웹 UI 포트는?
a) `80`  
b) `3000`  
c) `8080`  
d) `443`

**정답: ______**

---

### Q4-5. 로그인 기능 활성화 환경 변수 값은? (보안 권장)
a) `true`  
b) `false`  
c) `yes`  
d) `no`

**정답: ______**

---

### Q4-6. 기본 언어 설정 환경 변수 값은?
a) `ko_KR`  
b) `en_US`  
c) `zh_CN`  
d) `ja_JP`

**정답: ______**

---

### Q4-7~8. Documents와 Downloads 볼륨의 마운트 옵션은? (읽기 전용)
a) `rw`  
b) `ro`  
c) `read-only`  
d) `r`

**정답: ______, ______**

---

### Q4-9. Stirling PDF의 cpu_shares 값은? (PDF 편집)
a) `50`  
b) `70`  
c) `80`  
d) `90`

**정답: ______**

---

### Q4-10. main 값은?
a) `stirling`  
b) `stirling-pdf`  
c) `stirlingpdf`  
d) `pdf`

**정답: ______**

---

### Q4-11. Stirling PDF의 카테고리는?
a) `Backup`  
b) `Cloud`  
c) `Utilities`  
d) `Media`

**정답: ______**

---

### Q4-12. webui_port 값은?
a) `80`  
b) `3000`  
c) `8080`  
d) `443`

**정답: ______**

---

### Q4-13. store_app_id 값은?
a) `stirlingpdf`  
b) `stirling-pdf`  
c) `Stirling-PDF`  
d) `stirling_pdf`

**정답: ______**

---

### Q4-14. is_uncontrolled 값은?
a) `true`  
b) `false`

**정답: ______**

---

## 🎯 보너스 질문

### QB-1. CasaOS에서 $AppID 변수는 무엇을 의미하나요?
a) 컨테이너 ID  
b) 앱 이름 (name 값)  
c) 사용자 ID  
d) 포트 번호

**정답: ______**

---

### QB-2. NSL Router를 사용할 때 생성되는 도메인 패턴은?
a) `https://username.nsl.sh/appname`  
b) `https://appname.nsl.sh`  
c) `https://appname-username.nsl.sh`  
d) `https://nsl.sh/appname-username`

**정답: ______**

---

### QB-3. CasaOS 시스템 변수가 아닌 것은?
a) `$PUID`  
b) `$PGID`  
c) `$TZ`  
d) `$USERNAME`

**정답: ______**

---

### QB-4. rationale.md 파일이 필요한 경우는?
a) 앱이 root 권한이 필요할 때  
b) 앱이 port 80을 사용할 때  
c) 앱이 다국어를 지원할 때  
d) 앱이 CPU shares를 사용할 때

**정답: ______**

---

### QB-5. pre-install-cmd를 사용할 때 지켜야 할 보안 규칙이 아닌 것은?
a) 특정 버전 태그 사용 (:latest 금지)  
b) 사용자 디렉토리 작업 시 --user $PUID:$PGID 사용  
c) 반드시 Alpine Linux 사용  
d) 여러 번 실행해도 안전하도록 작성 (멱등성)

**정답: ______**

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

4. ✅ 완료 후 강사에게 확인 받기!

---

## 💡 학습 팁

- 막히는 문제가 있으면 `01-complete-example.yml` 파일을 참고하세요
- `CONTRIBUTING.md`와 `CLAUDE.md` 파일도 도움이 됩니다
- 정답을 찾는 것보다 *왜* 그런지 이해하는 것이 중요합니다!

**화이팅! 🚀**
