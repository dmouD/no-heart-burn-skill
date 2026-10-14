

# 🔥 不烧心 no-heart-burn-skill

**你说得对。但字不能乱改。**

让 AI 回答问题、汇报进度、写小剧场时，按「不烧心公式」说话。

公式要锁，槽位要稳，事实不能编。

宁可慢一点，也不能坏了规矩。

官网：<https://no-heart-burn-skill.aionly.fans>


[![npm version](https://img.shields.io/npm/v/no-heart-burn-skill?style=for-the-badge&logo=npm)](https://www.npmjs.com/package/no-heart-burn-skill)
[![npm downloads](https://img.shields.io/npm/dm/no-heart-burn-skill?style=for-the-badge&logo=npm)](https://www.npmjs.com/package/no-heart-burn-skill)
[![GitHub stars](https://img.shields.io/github/stars/dmouD/no-heart-burn-skill?style=for-the-badge&logo=github)](https://github.com/dmouD/no-heart-burn-skill)
[![GitHub last commit](https://img.shields.io/github/last-commit/dmouD/no-heart-burn-skill?style=for-the-badge&logo=git)](https://github.com/dmouD/no-heart-burn-skill/commits/main/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)](LICENSE)


---

[快速开始](#快速开始) · [如何使用](#如何使用) · [效果示例](#效果示例) · [工作规矩](#工作规矩) · [文件结构](#文件结构) · [许可](#许可)

## 这是什么

先把规矩立住，路才能越走越宽。`no-heart-burn-skill` 用 **15 个句式公式、22 条固定原句和工作阶段模板**，把真实答案装进短句、排比、递进和自问自答里。

先把答案讲清，再套公式。内容必须是真的，公式必须像，槽位可以换，原句不能乱改。

| 场景 | 怎么说 |
| --- | --- |
| 知识问答 | 先给定义，再讲机制、举例子，最后按公式收口。 |
| 工作汇报 | 开工要说，推进要报，受阻要讲，交付要清。 |
| 精确引用 | 字、标点、空格照原句保留，衍生句只替换槽位。 |
| 虚构文案 | 小事先摆出来，流程再叠上去，反转接住了，再说不烧心。 |

规则入口见 [SKILL.md](no-heart-burn-skill/SKILL.md)。以下安装与调用步骤以 Codex 为例。

## 快速开始

安装完了，再放进项目；目录放对了，再开口。选择 skills CLI 或 GitHub 安装即可。

### 通过 skills CLI 安装

在**目标项目根目录**执行：

```bash
npx skills add dmouD/no-heart-burn-skill
```

CLI 会克隆仓库、找到 `SKILL.md`，再让你选 agent 和安装方式；装完后 Codex 从项目的 `.agents/skills/` 读取技能。想一次到位、不再询问，就带参数执行：

```bash
npx skills add dmouD/no-heart-burn-skill -a codex -y
```

命令与选项见 [skills CLI 文档](https://www.skills.sh/docs/cli)。

### 通过 GitHub 安装

先克隆仓库，再复制其中的技能目录。把 `target_project` 换成你要使用技能的项目路径：

```bash
git clone https://github.com/dmouD/no-heart-burn-skill.git
cd no-heart-burn-skill

target_project="/path/to/your-project"
mkdir -p "$target_project/.agents/skills"
cp -R no-heart-burn-skill "$target_project/.agents/skills/"
```

两种方式的最终入口都是：

```text
你的项目/.agents/skills/no-heart-burn-skill/SKILL.md
```

安装后在目标项目中打开 Codex。若技能列表尚未显示，重启 Codex，再用 `/skills` 查找。目录与调用方式见 [OpenAI 官方技能说明](https://learn.chatgpt.com/docs/build-skills)。

## 如何使用

问题怎么办？先答。在 Codex 对话里显式调用：

```text
$no-heart-burn-skill 告诉我 Git 是什么。
```

也可以直接说“读取技能＋问题”：

```text
读取 no-heart-burn-skill，告诉我 RL 是什么。
```

读完规矩，再解释概念。技能提供表达方式，问题本身决定要讲什么知识。

工作与创作也可以这样用：

```text
$no-heart-burn-skill 检查这次修改，并按这个口吻汇报结果。
$no-heart-burn-skill 写一段“只改一个字，最后回滚”的虚构小剧场。
```

启用后，同一次任务的自然语言回复持续使用这个口吻。想换回来怎么办？说“恢复普通表达”，或明确指定其他输出格式。

## 效果示例

### 知识问答

提问：`Git 是什么？`

> Git 是分布式版本控制系统，用来记录文件变化、保存历史并协作开发。
>
> 先把规矩立住，路才能越走越宽。工作区、暂存区、提交历史，三个概念得先分开。
>
> `git add` 要暂存改动，`git commit` 要记录提交，`git log` 要查看历史。
>
> 不是我稳，是不能慌，一慌就容易做错事。改动暂存了，再提交，才会形成提交记录。
>
> 规矩不能坏，讲清了不烧心。

### 工作汇报

示例状态：README 中一处“确认”已改成“确定”，已检查差异，未运行测试。

> 字改好了。README 里一处“确认”改成“确定”。
>
> 宁可慢一点，也不能坏了规矩。
>
> 不是我稳，是不能慌，一慌就容易做错事。差异看过了，改动只有这一处；测试未运行。
>
> 不怕耗时吗？怕。更怕字改了，账却不清。
>
> 规矩不能坏，改了不烧心。

## 工作规矩

先把规矩立住，路才能越走越宽。原句要准，答案要真，格式也要合要求。

- **原句照用**：保留字、标点和空格；衍生句只替换公式槽位。
- **事实照报**：做完的写结果，未做的写“未做”，失败的说明问题，下一步用“先……再……”。
- **句式成组**：默认连续使用 3—5 组公式，至少保留两句完整骨架。
- **格式按要求**：代码、命令、路径和报错保持准确；明确要求一句话、JSON 或其他格式时，按新要求输出。
- **创作说清楚**：段子和夸张流程用于用户明确要求的虚构文案，实际工作汇报填写真实状态。

## 文件结构

```text
no-heart-burn-skill/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── corpus.md
    └── original/
        ├── 1.md
        ├── 2.md
        └── 中转规矩.md
```

入口要清，原句要齐，显示信息也要对：

- [SKILL.md](no-heart-burn-skill/SKILL.md)：调用规则、15 个句式公式，以及知识问答和阶段模板。
- [corpus.md](no-heart-burn-skill/references/corpus.md)：22 条固定原句、来源优先级和文风参考。
- [original/](no-heart-burn-skill/references/original/)：工程版、训练版和中转版原文归档。
- [openai.yaml](no-heart-burn-skill/agents/openai.yaml)：技能显示名、说明和默认调用提示。

## 许可

本项目采用 [MIT License](LICENSE)，版权为 `Copyright (c) 2026 dmouD`。许可要读，声明要留，使用与分发按许可条件执行。

规矩不能坏，用着不烧心。
