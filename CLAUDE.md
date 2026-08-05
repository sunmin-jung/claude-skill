# CLAUDE.md — 팀 공용 Claude 지침

React + TypeScript + Vite 프로젝트. 팀원 4명 공통 적용.

---

## 프로젝트 구조

```
my-app/
  src/        ← 소스코드
  index.html
  vite.config.ts
  tsconfig.json
```

**스택:** React 19 · TypeScript 6 · Vite 8

---

## 브랜치 구조

```
main                  ← 최종 배포. 건드리지 말 것
  └── dev             ← 통합 브랜치. PR로만 머지
        ├── feature/팀원1이름
        ├── feature/팀원2이름
        ├── feature/팀원3이름
        └── feature/팀원4이름
```

---

## 브랜치 작업 순서

**1. 시작 전 dev 최신화**
```bash
git checkout dev
git pull origin dev
```

**2. 내 브랜치 생성**
```bash
git checkout -b feature/내이름
```

**3. 작업 후 push**
```bash
git add .
git commit -m "feat: 기능 설명"
git push origin feature/내이름
```

**4. GitHub에서 PR 생성**
- 대상 브랜치: `dev` (main 아님)
- 제목: `[이름] 기능 설명` 예) `[민준] 로그인 페이지 추가`

---

## PR 규칙

- 최소 1명 수락 후 머지
- 본인 PR 본인 머지 금지
- 충돌 있으면 본인이 해결 후 다시 PR
- dev → main 머지는 팀장만

---

## 금지사항

- `main` 직접 push 금지
- `dev` 직접 push 금지
- 남의 브랜치 파일 수정 금지
- `.env`, `*.key` 커밋 금지
- `node_modules/` 커밋 금지

---

## 커밋 메시지 규칙

```
feat: 새 기능 추가
fix: 버그 수정
style: 스타일/포맷 변경
refactor: 리팩토링
chore: 설정, 패키지 등 기타
```

---

## 개발 명령어

```bash
cd my-app
npm install       # 처음 설치
npm run dev       # 로컬 서버 (localhost:5173)
npm run build     # 빌드
npm run lint      # 린트 검사
```

---

## PR 머지 전 체크리스트

- [ ] `npm run lint` 오류 없음
- [ ] `npm run build` 성공
- [ ] 로컬에서 기능 동작 확인
- [ ] `.env` 파일 커밋 안 됨
- [ ] PR 대상이 `dev` 인지 확인

---

## Claude study 스킬 설치 (팀원 전원)

PowerShell에 아래 명령어 붙여넣기:

```powershell
mkdir "$env:USERPROFILE\.claude\skills\study" -Force; Invoke-WebRequest -Uri "https://raw.githubusercontent.com/sunmin-jung/claude-skill/main/study/SKILL.md" -OutFile "$env:USERPROFILE\.claude\skills\study\SKILL.md"
```

완료 후 Claude Code 켜서 `/study` 입력하면 바로 사용 가능.

---

## GitHub 브랜치 보호 설정 (팀장만)

GitHub → 레포 → Settings → Branches → Add branch protection rule

**main:**
```
Branch name pattern: main
✅ Require a pull request before merging
✅ Require approvals: 1
✅ Do not allow bypassing the above settings
```

**dev:**
```
Branch name pattern: dev
✅ Require a pull request before merging
✅ Require approvals: 1
```
