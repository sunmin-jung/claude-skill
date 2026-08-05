# study 스킬 설치 방법 (Windows)

## 1. PowerShell 열기
시작 → PowerShell 검색 → 실행

## 2. 아래 명령어 붙여넣기

```powershell
mkdir "$env:USERPROFILE\.claude\skills\study" -Force; Invoke-WebRequest -Uri "https://raw.githubusercontent.com/sunmin-jung/claude-skill/main/study/SKILL.md" -OutFile "$env:USERPROFILE\.claude\skills\study\SKILL.md"
```

## 3. Claude Code 실행

```
claude
```

## 4. 스킬 사용

```
/study
```

입력하면 TypeScript 학습 세션 시작.
