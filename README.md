<!-- README_SYNC: source=fddf931752256d3da7cc33399717aedafc146de6; updated=2026-11-18 -->

简体中文 · [English](./README_EN.md)

# 飞书项目文档与周报写作

用这个 Codex Skill，把仓库里实际完成的工作整理成中文项目介绍、研究计划或周报。没参与日常开发的同事也能看清做了什么、有哪些证据、接下来要做什么。

## 在 Codex 中试用

下例克隆本仓库，再把 [SKILL.md](./SKILL.md) 和 [Agent 元数据](./agents/openai.yaml) 放进 Codex 的技能目录；若目标已存在，先比较版本，避免覆盖。

```bash
git clone https://github.com/LikC1606/feishu-project-report-writing.git
cd feishu-project-report-writing
skill_dir="${CODEX_HOME:-$HOME/.codex}/skills/feishu-project-report-writing"
mkdir -p "$(dirname "$skill_dir")"
mkdir "$skill_dir" && cp -a SKILL.md agents "$skill_dir/"
```

新开会话，给出仓库、时间范围和目标文档。先在本地试一份草稿：

> 用 $feishu-project-report-writing 根据当前代码撰写本期中文周报。核对相关提交与验证记录，先写已完成，再写下周计划，先只生成本地 Markdown。

本地起草可直接使用项目材料。需要更新飞书正文时使用 `lark-doc`，只有改知识库目录时才需要 `lark-wiki`。

## 三种文档怎么写

| 文档 | 怎么组织 |
| --- | --- |
| 项目介绍 | 首屏说清定位、当前能力和导航。每周成果与计划留在周报。 |
| 研究计划 | 先指出当前不足，再选少数能推进长期目标的方向。每条讲清预期改进。 |
| 工作周报 | 标实际日期范围；一期内先成果后计划，新一期置顶，保留旧记录。 |

以相关提交、实现和验证记录为依据，区分已合入、仍在分支、工作区未提交、已部署和待验证。没有验证的效果列为待验证目标。当期无证据的旧功能不会计作本周成果。

每篇和每个模块最多 200 行或可见逻辑段落。计划默认约 4 条、每条一句且正文不超过 100 字；用标题层级保留目录，必要时归档旧周次。

## 更新飞书时

授权更新后，先取最新正文和修订版本，在原文的目标段落做增量修改，保留导航、引用、附件与历史。写入结果不确定时先回读，实际核对正文、顺序和关系后才报告已更新。完整写作和交付约定在 [SKILL.md](./SKILL.md)。
