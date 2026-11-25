# OpenSource Automation Lab

Public research and documentation for two independent engineering tracks: **competition opportunity automation** and **JARVIS**, a privacy-conscious AI assistant.

> **Project maturity:** Documentation and design exploration. This repository does **not** claim a deployed assistant, working competition scraper, verified integrations, or external adoption.

## Projects

| Track | Purpose | Current public status |
| --- | --- | --- |
| [Competition automation](competition-automation/README.md) | Discover, review, deduplicate, and track competition and program notices with source provenance. | Proposed architecture and verification roadmap |
| [JARVIS](jarvis/README.md) | Explore Korean-language assistant architecture, grounded retrieval, memory lifecycle, safe tool execution, and speech interfaces. | Public-safe research overview; private implementation remains separate |

## Principles

- **Evidence over claims:** Separate verified functionality, design proposals, and untested ideas.
- **Privacy by design:** No private notes, credentials, personal memory databases, or sensitive configuration are published here.
- **Reproducibility:** Add tests and documented evaluation criteria before announcing operational capabilities.
- **Respectful automation:** Prefer permitted official sources, preserve citations and timestamps, and keep consequential actions under human control.
- **Preserve existing work:** This repository does not replace or migrate the original projects.

## Documentation

- [Project status and evidence](docs/PROJECT_STATUS.md)
- [Contributing](CONTRIBUTING.md)
- [Security and privacy](SECURITY.md)

## Roadmap

1. Curate permission-cleared technical documentation and source provenance.
2. Publish independently authored, non-sensitive examples and fixture-based tests.
3. Verify individual modules in isolation before describing them as functional.
4. Document reproducible integration results and limitations.

## License

No license has been granted yet. A license will be selected after reviewing ownership and third-party materials. Public visibility alone does not grant reuse rights.

---

# 한국어 안내

이 저장소는 **대회·공모전 자동화**와 **JARVIS 개인 AI 비서** 프로젝트의 공개 가능한 설계 및 연구 문서를 모아 둔 공간입니다. 현재 공개된 문서는 실제 배포나 동작 검증을 의미하지 않습니다. 기존 비공개 프로젝트의 코드, 개인 데이터, 인증정보는 옮기지 않았습니다.

- [대회 자동화](competition-automation/README.md)
- [JARVIS](jarvis/README.md)
- [검증된 현황과 미확인 사항](docs/PROJECT_STATUS.md)

## Continue work from GitHub (ChatGPT Work / coding agent)

**Read before editing:** [Competition recovery handoff](https://github.com/errorrelooad/OpenSource-Automation-Lab/blob/docs/competition-observability-playbook/competition-automation/RECOVERY_HANDOFF.md), [observability plan](https://github.com/errorrelooad/OpenSource-Automation-Lab/blob/docs/competition-observability-playbook/competition-automation/OBSERVABILITY_PLAYBOOK.md), and [draft PR #1](https://github.com/errorrelooad/OpenSource-Automation-Lab/pull/1). Cross-project handoff: [private JARVIS Work continuation](https://github.com/errorrelooad/JARVIS/blob/docs/ai-observability-playbook/docs/WORK_CONTINUATION.md) (requires access).

The canonical private competition source destination is `errorrelooad/competition-automation` (initialization/source migration pending). This public repository is for cleared documentation only. The original competition project includes Kaggle/DACON solution automation, not only announcement discovery. Review ChatGPT Library `/대회 매크로` archives, compare and scan candidates before any import. Preserve existing data, never commit credentials or private datasets, and require explicit approval for external submissions. The user-provided Datadog AI Playbook informs evaluation, observability and governance; it is not proof of working integration. BC-250 is discontinued and excluded.
