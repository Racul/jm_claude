# jm_claude

데이터 과제를 5단계 문서화 워크플로우로 진행하기 위한 Claude Code / Codex 설정 세트.

```
jm_claude/
├── CLAUDE.md          # 진행 순서와 공통 규칙 (Codex 에서는 AGENTS.md 로 사용)
└── skills/
    ├── coding-guidelines/   # 코딩 원칙
    ├── prob-describe/       # 1단계: 문제 정의
    ├── plan/                # 2단계: 계획 + test 계획
    ├── data-audit/          # 3단계: 데이터 함정 검사
    ├── progress-record/     # 4단계: 실행 기록
    └── result/              # 5단계: 최종 결과
```

산출 문서는 작업 프로젝트의 `docs/` 폴더에 생성된다.

## 1. 클론

```bash
git clone https://github.com/Racul/jm_claude.git ~/jm_claude
```

## 2. 작업 프로젝트에 공통 파일 복사

작업할 프로젝트 루트에서 실행한다. `CLAUDE.md` 가 `skills/<name>` 경로를 참조하므로 `skills/` 를 프로젝트 루트에 함께 둔다.

```bash
cd <프로젝트 경로>
cp ~/jm_claude/CLAUDE.md .
cp -r ~/jm_claude/skills .
```

## 3. Claude Code 적용

Claude Code 는 프로젝트 루트의 `CLAUDE.md` 를 자동으로 읽는다. skill 을 이름으로 자동 로드하려면 `.claude/skills/` 에도 복사한다.

```bash
mkdir -p .claude
cp -r skills .claude/skills
```

확인:

```bash
claude
```

- `/skills` 목록에 `prob-describe`, `plan`, `data-audit`, `progress-record`, `result`, `coding-guidelines` 가 보이는지 확인
- "진행 순서를 요약해줘" 라고 물어 5단계가 나오는지 확인

## 4. Codex 적용

Codex 는 `CLAUDE.md` 대신 프로젝트 루트의 `AGENTS.md` 를 읽는다. 같은 내용으로 만든다.

```bash
cp CLAUDE.md AGENTS.md
```

skill 을 Codex 에서 이름으로 사용하려면 사용자 skill 폴더에 복사한다. 이미 같은 이름의 skill 이 있으면 덮어쓰지 않도록 `-n` 을 쓴다.

```bash
mkdir -p ~/.codex/skills
cp -rn skills/* ~/.codex/skills/
```

확인:

```bash
codex
```

- "AGENTS.md 의 진행 순서를 요약해줘" 라고 물어 5단계가 나오는지 확인

## 5. 사용

에이전트에게 과제를 주고 1단계부터 시작하게 한다.

```
과제 파일은 <경로> 에 있다. CLAUDE.md 의 Stage Order 대로 1단계부터 진행하라.
```

진행 결과:

```
<프로젝트>/docs/
├── prob_describe.md
├── plan.md
├── data_audit.md
├── progress_record.md
└── result.md
```

## 업데이트

```bash
cd ~/jm_claude && git pull
```

`git pull` 은 클론 폴더만 갱신한다. 작업 프로젝트에 복사한 파일은 2~4단계 복사를 다시 실행해야 반영된다.
