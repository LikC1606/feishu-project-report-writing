<!-- README_SYNC: source=fddf931752256d3da7cc33399717aedafc146de6; updated=2026-11-18 -->

[简体中文](./README.md) · English

# Feishu Project Report Writing

A Codex Skill for Chinese project briefs, research plans, and weekly reports grounded in the repository. It helps readers outside day-to-day development see what changed, what is supported by the evidence, and what comes next.

## Try it in Codex

The example clones this repository and installs [SKILL.md](./SKILL.md) with its [agent metadata](./agents/openai.yaml). Compare with an existing installation before replacing it.

```bash
git clone https://github.com/LikC1606/feishu-project-report-writing.git
cd feishu-project-report-writing
skill_dir="${CODEX_HOME:-$HOME/.codex}/skills/feishu-project-report-writing"
mkdir -p "$(dirname "$skill_dir")"
mkdir "$skill_dir" && cp -a SKILL.md agents "$skill_dir/"
```

Open a new session and specify the repository, reporting dates, and intended document. For a first local draft, ask:

> Use $feishu-project-report-writing to draft this week's report in Chinese from the current code. Check the relevant changes and verification records, put completed work before next week's plan, and create local Markdown only.

Local drafting uses the project material. Editing a Feishu document uses `lark-doc`; changes to the knowledge-base navigation use `lark-wiki`.

## Choose the document

| Document | What it should do |
| --- | --- |
| Project brief | Put purpose, current capabilities, and navigation upfront. Keep weekly changes and plans in their own reports. |
| Research plan | Start with the current gap and choose a few directions that advance the larger goal. State what each direction should improve. |
| Weekly report | Use the actual date range; place completed work before the plan, with the newest report first and old entries retained. |

Use relevant commits, implementations, and verification records to distinguish merged work, branch work, uncommitted changes, deployment, and pending verification. If an effect has not been validated, present it as a validation goal. Count only work supported by evidence within the reporting period.

Each document and module is capped at 200 text lines or visible blocks. A plan normally has about four items, each one sentence of at most 100 Chinese characters. Preserve heading navigation and archive older weeks when needed.

## Update Feishu when authorized

Read the latest document and revision, then update only the intended passages while preserving navigation, references, attachments, and history. If a write result is uncertain, read it back first. Report an update once the revised content and structure have been checked. See [SKILL.md](./SKILL.md) for the full writing and delivery rules.
