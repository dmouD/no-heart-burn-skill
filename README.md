# no-heart-burn-skill

一个“不烧心”口吻的 Codex Skill：把知识解释、工作进度和创作文案写成短句、排比、自问自答和郑重的“立规矩”台词。

规则入口见 [SKILL.md](no-heart-burn-skill/SKILL.md)。

## 看看效果

输入：

```text
$no-heart-burn-skill 帮我把 README.md 中的“确认”改成“确定”，先说说你准备怎么做。
```

开工回复示例：

```text
你说得对。但字不能乱改。
先把规矩立住，路才能越走越宽。README.md 里的“确认”，得先看清每一处上下文。
原文要读，位置要找，差异要看。
读完了，再改需要替换的字；改完了，再检查差异。
宁可慢一点，也不能坏了规矩。
```

这段展示的是准备执行的动作。实际交付时，改了什么、检查了什么、遇到什么问题，都按真实结果填写。

## 能做什么

- **15 个句式公式**：从“你说得对”到“规矩不能坏”，覆盖承接、排比、推进、自问自答和收口。
- **知识问答**：先回答问题，再用固定台词解释机制、举例和澄清易混点。
- **阶段输出**：提供开工、推进、受阻和交付模板，让同一次任务持续使用这个口吻。
- **创作文案**：用户明确要求段子、小剧场或完整仿写时，按“小事，大规矩”的节奏展开。
- **原句与语料**：保留工程版、训练版和中转版原文，原句照抄，衍生句只替换公式槽位。

代码、命令、路径、报错和用户指定的原文保持准确；口吻用在面向用户的叙述中。

## 仓库目录

```text
.
├── README.md
├── .gitignore
├── .gitattributes
└── no-heart-burn-skill/
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

`SKILL.md` 是技能入口；`agents/openai.yaml` 提供显示信息；`references/` 保存原句库和原文归档。`dist/no-heart-burn-skill.zip` 是独立技能包，`dist/no-heart-burn-skill-github.zip` 是包含 README 等文件的仓库包；`dist/` 不入 Git。

## 安装到项目

1. 下载并解压本仓库，或使用本仓库的实际地址 `clone` 到本地。
2. 将其中的整个 `no-heart-burn-skill/` 文件夹复制到目标项目的 `.agents/skills/` 下。下面的两个路径需要换成自己的目录：

   ```bash
   skill_repo="/path/to/downloaded-repo"
   target_project="/path/to/your-project"
   mkdir -p "$target_project/.agents/skills"
   cp -R "$skill_repo/no-heart-burn-skill" "$target_project/.agents/skills/"
   ```

3. 确认安装后的入口是 `.agents/skills/no-heart-burn-skill/SKILL.md`，在目标项目中打开 Codex 并调用技能。若未出现在技能列表中，重启 Codex。

项目技能目录与调用方式见 [OpenAI 官方技能说明](https://learn.chatgpt.com/docs/build-skills)。

## 使用

显式调用：

```text
$no-heart-burn-skill 告诉我 RL 是什么。
```

也可以直接提出“读取技能＋知识问题”：

```text
读取 no-heart-burn-skill，告诉我 RL 是什么。
```

这会应用技能的表达规则来解释强化学习，包括定义、机制和例子。知识问题的范围由问题本身决定，无需先在技能语料中找到这个概念。

工作任务与创作示例：

```text
$no-heart-burn-skill 检查这次修改，并用这个口吻汇报结果。
$no-heart-burn-skill 写一段“给备份做备份”的虚构小剧场。
```

启用后，同一次任务的后续自然语言回复持续使用该口吻；明确要求“恢复普通表达”或指定其他输出格式即可切换。

## 上传到 GitHub

建议仓库名使用 `no-heart-burn-skill`。在 GitHub 创建一个空仓库后，在已提交初始版本的本地仓库根目录执行下面的命令；先将第一行替换为 GitHub 页面提供的实际仓库地址：

```bash
github_repo_url='替换为 GitHub 仓库的 HTTPS 或 SSH 地址'
git remote add origin "$github_repo_url"
git push -u origin main
```
