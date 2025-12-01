# 정답 파일 - 강사용 📚

## 📂 이 폴더의 내용

이 폴더에는 워크샵 실습 파일의 **정답**이 들어있습니다.

⚠️ **주의**: 이 폴더는 **강사용**입니다. 학생들에게는 공개하지 마세요!

---

## 📋 파일 목록

### 정답 Docker Compose 파일 (완성본)
- `02-qbittorrent-answer.yml` - qBittorrent 정답
- `03-convertx-answer.yml` - ConvertX 정답
- `04-filebrowser-answer.yml` - FileBrowser 정답
- `05-stirling-pdf-answer.yml` - Stirling PDF 정답

### 채점 가이드
- `ANSWER_SUMMARY.md` - 빠른 채점을 위한 정답 요약표
  - 모든 빈칸의 정답을 표로 정리
  - 채점 시트 포함
  - 자주 틀리는 부분 안내

---

## 🎯 사용 방법

### 1. 빠른 채점
학생의 답안을 확인할 때:
1. `ANSWER_SUMMARY.md` 열기
2. 해당 실습의 정답 표 확인
3. 학생 답안과 비교하며 채점

### 2. 상세 비교
답안이 애매하거나 검증이 필요할 때:
1. 해당 정답 파일 열기 (예: `02-qbittorrent-answer.yml`)
2. 학생의 파일과 나란히 비교
3. 전체 구조와 문맥 확인

### 3. 검증 실행
정답 파일도 실제로 작동하는지 확인 가능:
```bash
# 문법 검증
docker-compose -f 02-qbittorrent-answer.yml config

# 실제 테스트 (선택)
docker-compose -f 02-qbittorrent-answer.yml up -d
```

---

## ✅ 채점 체크리스트

### 필수 확인 사항
각 학생의 답안을 채점할 때:

#### 🔰 실습 1: qBittorrent
- [ ] user: $PUID:$PGID 설정
- [ ] 이미지: lscr.io/linuxserver/qbittorrent:5.1.2
- [ ] expose: 80
- [ ] webui_port: 80
- [ ] cpu_shares: 20
- [ ] Downloads 볼륨 매핑

#### 🔸 실습 2: ConvertX
- [ ] user: "0:0" (Root 권한)
- [ ] PUID=0, PGID=0
- [ ] :ro 옵션 (읽기 전용)
- [ ] memory: 2G
- [ ] webui_port: 3000

#### 🔹 실습 3: FileBrowser
- [ ] /DATA 전체 마운트
- [ ] environment에 PUID/PGID
- [ ] network_mode: bridge
- [ ] cpu_shares: 80

#### 🚀 실습 4: Stirling PDF
- [ ] user: $PUID:$PGID
- [ ] SECURITY_ENABLELOGIN=true
- [ ] memory: 4G
- [ ] 4개 볼륨 모두 매핑
- [ ] :ro 옵션 2곳
- [ ] cpu_shares: 70

---

## 📊 점수 배정 (권장)

### 객관적 평가 (70점)
- 빈칸 정답률: 각 실습당 정답 개수 / 총 빈칸 개수
- qBittorrent (18개): 18점
- ConvertX (15개): 15점
- FileBrowser (12개): 12점
- Stirling PDF (16개): 16점
- **소계: 61점 만점**

### 개념 이해도 (30점)
구두 질문 3개 × 10점:
1. 권한 관리 이해도 (10점)
2. NSL Router 이해도 (10점)
3. CPU Shares 이해도 (10점)

### 합격 기준
- **80점 이상**: 우수 (조기 퇴실)
- **70-79점**: 양호 (수정 후 재제출)
- **60-69점**: 보충 필요 (개념 설명 후 재시도)
- **60점 미만**: 추가 학습 필요

---

## 🎓 피드백 가이드

### 잘한 점 (강화할 부분)
- 정확한 이미지 태그 사용
- 올바른 권한 설정
- 깔끔한 코드 구조

### 개선할 점 (건설적 피드백)
```
"expose와 webui_port가 일치하지 않네요. 
NSL Router를 사용할 때는 두 값이 같아야 합니다.
01-complete-example.yml의 2-5번 섹션을 다시 확인해보세요!"
```

### 자주 하는 실수별 대응
1. **:latest 사용**
   → "특정 버전 태그가 필요한 이유 설명"
   
2. **권한 누락**
   → "사용자 디렉토리 접근 시 권한이 왜 필요한지 설명"
   
3. **ports vs expose**
   → "NSL Router 작동 방식 설명"

---

## 💡 시간 관리 팁

### 효율적인 채점 순서
1. **1차: 빠른 스캔** (1분/학생)
   - ANSWER_SUMMARY.md 보며 주요 빈칸만 확인
   
2. **2차: 문법 검증** (30초/파일)
   ```bash
   docker-compose -f 학생파일.yml config
   ```
   
3. **3차: 개념 확인** (2-3분/학생)
   - 구두 질문 3개

**총 소요 시간**: 약 5-7분/학생

---

## 🔄 답안 변형 처리

### 허용 가능한 변형
학생이 다르게 작성했어도 정답으로 인정:

1. **볼륨 경로**
   ```yaml
   # 둘 다 정답
   - /DATA/AppData/qbittorrent/config:/config
   - /DATA/AppData/$AppID/config:/config
   ```

2. **환경 변수 순서**
   - 순서가 바뀌어도 OK

3. **주석**
   - 학생이 추가한 주석은 OK

4. **공백/들여쓰기**
   - YAML 문법만 맞으면 OK

### 불허 사항
반드시 감점:

1. **:latest 태그**
   - 보안 규칙 위반

2. **포트 불일치**
   - expose ≠ webui_port

3. **권한 누락**
   - 사용자 디렉토리 접근 시

4. **필수 필드 누락**
   - main, webui_port 등

---

## 📞 문의 및 지원

채점 중 어려운 케이스:
1. ANSWER_SUMMARY.md의 "자주 틀리는 부분" 참고
2. 01-complete-example.yml의 주석 참고
3. README.md의 "문제 해결" 섹션 참고

---

**채점 화이팅! 💪**

*학생들의 성장을 도와주셔서 감사합니다!*
