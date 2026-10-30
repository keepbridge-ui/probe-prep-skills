# 설계 출처와 고정 기준

확인일: 2026-10-30 UTC. 공개 원본의 원칙을 선별해 세 스킬을 독자 한국어 문구로 작성했다. 원문 지침의 전문·번역본, 실행 스크립트, 하네스는 패키지에 포함하지 않았다. 아래 설명은 이 패키지의 선택을 요약하며 원저자의 전체 워크플로와 동일하다는 뜻이 아니다.

## 기준 원본

| 범위 | 기준 커밋 | 라이선스 |
| --- | --- | --- |
| cursor/plugins pstack 0.15.36 | `4dd1d05818d19792e7cd6e818f1667f95f7e1dbe` | pstack/LICENSE, MIT, © 2026 Lauren Tan |
| obra/superpowers | `2ce8aa15d05bd57213e6f746f953aafb7ded7a8b` | 루트 LICENSE, MIT, © 2025 Jesse Vincent |

GitHub API로 main 커밋을 고정한 뒤 해당 SHA의 raw 원문을 직접 확인했다. 선택 영역의 LICENSE 경로를 조사했다. cursor/plugins 저장소 루트에는 LICENSE가 없으며 pstack의 MIT를 저장소 전체에 일반화하지 않았다. 저작권·허가·면책 고지 전문은 [제3자 고지](THIRD_PARTY_NOTICES.md)에 연결했다.

## 선별한 원칙

| 참고 원문 | 이 패키지가 선별한 원칙 | 반영 위치 |
| --- | --- | --- |
| [in-your-own-words](https://github.com/cursor/plugins/blob/4dd1d05818d19792e7cd6e818f1667f95f7e1dbe/pstack/skills/in-your-own-words/SKILL.md) | 확정 요구를 짧게 재진술해 오해를 드러낸다. | plan |
| [sharpen](https://github.com/cursor/plugins/blob/4dd1d05818d19792e7cd6e818f1667f95f7e1dbe/pstack/skills/sharpen/SKILL.md) | 원자료·방법·독립적인 성공 근거를 점검한다. | plan |
| [tdd](https://github.com/cursor/plugins/blob/4dd1d05818d19792e7cd6e818f1667f95f7e1dbe/pstack/skills/tdd/SKILL.md) | 적합한 작은 검사에서 실패를 확인하고 최소 수정 후 재검사한다. | build |
| [interrogate](https://github.com/cursor/plugins/blob/4dd1d05818d19792e7cd6e818f1667f95f7e1dbe/pstack/skills/interrogate/SKILL.md) | 구체적 코드 경로와 실행 근거로 결함 주장을 가린다. | check |
| [show-me-your-work](https://github.com/cursor/plugins/blob/4dd1d05818d19792e7cd6e818f1667f95f7e1dbe/pstack/skills/show-me-your-work/SKILL.md) | 핵심 선택·이유·증거·한계를 간결하게 기록한다. | 세 스킬의 결과 요약 |
| [systematic-debugging](https://github.com/obra/superpowers/blob/2ce8aa15d05bd57213e6f746f953aafb7ded7a8b/skills/systematic-debugging/SKILL.md) | 재현, 데이터 흐름, 가설 판별을 통해 원인에 맞춰 고친다. | build |
| [verification-before-completion](https://github.com/obra/superpowers/blob/2ce8aa15d05bd57213e6f746f953aafb7ded7a8b/skills/verification-before-completion/SKILL.md) | 완료 주장을 최신 검사 출력과 대조한다. | check |

현재 원본의 `tdd`는 명시 요청 또는 명확하고 저렴한 로컬 검사 경로를 중시하며, 새 하네스를 무조건 만들라는 지침이 아니다. `sharpen`은 목표·원자료·방법·성공 근거를 깊게 하는 지침이다. 시험 요구 자체를 임의로 고치거나 범위를 넓히는 방식으로 적용하지 않았다.

`interrogate` 원본의 arena·worktree·병렬 adversary, `show-me-your-work`의 transcript 수집·다른 모델 계열 감사, 브라우저 자동화 대체 검사와 commit·PR·배포 흐름은 가져오지 않았다. 검토 원칙을 허용된 로컬 구현·검증에만 적용했다.

## 재현용 파일 해시

[SOURCES.json](SOURCES.json)에 선택 원문 7개, 두 LICENSE, pstack manifest의 고정 raw URL·permalink·SHA256을 기록했다. 해시는 조사한 원본 바이트의 값이며 이 패키지의 SKILL.md 해시가 아니다. 원문 전문을 재배포하지 않아 이 패키지 안에서 원문 해시를 직접 계산할 수는 없다. 공개 원문을 같은 SHA로 다시 취득했을 때 비교할 수 있다.

## Codex 형식 근거

공식 [Build skills](https://learn.chatgpt.com/docs/build-skills)를 2026-10-30에 열어 확인했다. 프로젝트 `.agents/skills/<이름>/SKILL.md`, YAML의 `name`·`description`, `$skill-name` 명시 호출, `agents/openai.yaml`의 선택적 호출 정책을 사용한다. 문서는 변경 가능한 웹 문서이며 고정 커밋은 기록하지 않았다. `allow_implicit_invocation: false`는 호스트가 지원할 때 자동 호출을 막는 설정으로, 실제 시험 제공 버전에서 지원 확인이 필요하다. 이 패키지를 열거나 구조 검사한 것만으로 스킬 등록·호출 성공을 입증하지는 않는다.

## 시험 제한 근거의 한계

README.md에 적힌 시험 제한은 제작 시 전달받은 가이드 요약을 반영했다. 시험 가이드 원문 URL·실제 과제·제공 버전은 이 작업 환경에서 독립 확인하지 않았다. 공식 사용 허가나 최신 운영 규칙의 인증이 아니며, 실제 최신 안내와 충돌하면 그 안내를 따른다. 체험 환경 설정이 본시험에도 유지되는지는 미확인이다.
