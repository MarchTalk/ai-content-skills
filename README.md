# AI 内容技能集 · Content Creation Skills

[![Stars](https://img.shields.io/github/stars/MarchTalk/ai-content-skills?style=flat&color=yellow)](https://github.com/MarchTalk/ai-content-skills/stargazers)
[![License](https://img.shields.io/github/license/MarchTalk/ai-content-skills)](LICENSE)
[![Latest Release](https://img.shields.io/github/v/release/MarchTalk/ai-content-skills)](https://github.com/MarchTalk/ai-content-skills/releases)

> 一套给 AI 编程助手（Claude Code / Codex 等）用的中文内容创作技能，来自「隐拾三月·AI内容系统」的实战沉淀。
>
> A set of Chinese content-creation skills for AI coding agents (Claude Code, Codex, etc.), extracted from a working one-person content production system.

这不是提示词合集，是一套**带质检闸门的内容工作流零件**。每个技能都有明确的调用时机、工作步骤、输出格式和质检标准，AI 跑完能自查有没有做到位。

![demo](assets/demo.gif)

<sub>真实终端录制：clone 仓库 → 看技能目录 → 打开 `quality-gate` 的原文，其中一条硬规则是「AI 味一票否决」——不管质检结果其它项多好，AI 味太重直接判不通过。</sub>

<details>
<summary><strong>Read this in English</strong></summary>

<br>

This is not a prompt collection — it's a set of **quality-gated content workflow parts** for AI coding agents. Each skill has a clear trigger condition, a step-by-step process, an output format, and a quality checklist the agent can self-audit against.

**Why this exists.** The real failure mode when using AI to write content isn't "it can't write" — it's that the output is generic and shallow (no detail that required actually checking a source), reads as obviously AI-generated (mechanical parallelism, "not X but Y" reversals, templated openers), gets graded with the wrong rubric (grading a personal-opinion piece like a sales pitch), sounds convinced of its own draft without ever being pressure-tested, and repeats the same mistake you already corrected. These 9 skills were grown around exactly those problems, iterated over 6+ months on a real content account.

**Skills at a glance** — gates (`material-research` forces real research before writing, with an optional deepen-the-take step; `quality-gate` is the final checklist with an AI-tone veto), an adversarial review (`adversarial-gate` pressure-tests a thesis before you draft it, then audits the finished draft for sycophantic "polish without progress"), judgment layers (`buyer-psychology` for purchase resistance and unspoken user psychology, `concept-check` for catching empty jargon and fuzzy concepts), an organizer (`organize` turns a free-form deep-dig conversation into a faithful, complete draft), and workflow parts (`content-positioning`, `topic-strategy`, `platform-distribution`).

**Install:**
```bash
git clone https://github.com/MarchTalk/ai-content-skills.git
cp -r ai-content-skills/skills/* ~/.claude/skills/
```
Then restart Claude Code and call skills via `/quality-gate`, `/material-research`, etc., or just describe what you need — the skills are plain Markdown, so they also work in any agent that supports skill/instruction files (Codex included).

License: MIT. Full skill tables and the recommended pipeline are in the Chinese section below (skill names and file paths are in English regardless).

</details>

## 为什么会有这套东西

用 AI 写内容，最大的问题从来不是"写不出来"，而是：

- 写得**太泛太口水**——没有"只有查过才知道"的具体细节；
- **AI 味重**——"不是 X 而是 Y"翻转排比、工整对仗、模板开头；
- **拿错尺子**——用成交的标准去质检人设稿，用流量的标准去否观点稿；
- **同一个错误反复犯**——你纠正过的问题，下次它照样来。

这套技能就是围绕这四个问题长出来的，在真实账号上迭代了半年以上。

## 技能一览

### 闸门类（建议所有写稿流程强制串联）

| 技能 | 干什么 |
| --- | --- |
| [material-research](skills/material-research/) | **实料调研闸门**。动笔前强制跑：干货型必须联网查到真实案例 / 数字 / 一手细节，列"实料清单"，清单为空不许写；观点型显式放行。判据只有一条：删掉这条料，稿子会不会塌。额外带一步可选的"内核深化"——命题定稿后查最强反方观点，把判断本身逼深，不是为了引用。 |
| [quality-gate](skills/quality-gate/) | **最终质检闸门**。九条通用质检（空话 / 模板腔 / AI 腔 / 机械排比 / 书面词…）+ 按内容类型分清单质检 + AI 味一票否决 + 平台合规一票否决。不放水。 |

### 独立审核类

| 技能 | 干什么 |
| --- | --- |
| [adversarial-gate](skills/adversarial-gate/) | **压力对抗审核**。两种模式串行跑：命题定稿后起一个全新上下文的 agent 挑逻辑漏洞、找反例、判断是不是新瓶装旧酒；终稿质检通过后再核一遍——终稿是不是真的把判断往深处推了，还是只是包装得更顺口（谄媚检测），可选带一层历史稿件结构查重。默认姿态是先假定平庸，禁止清单打勾式审查，反共识判断不因为反共识被扣分。 |

### 底层判断类

| 技能 | 干什么 |
| --- | --- |
| [buyer-psychology](skills/buyer-psychology/) | 商业心理与购买阻力。真伪需求 → 产品翻译 → 六类购买阻力（钱/风险/时间/信任/面子/决策成本）→ 翻译成用户不会说出口的心理独白 → 六种锚点 → 内容角色 → 商业落点。落点必须是明天就能做的具体动作。 |
| [concept-check](skills/concept-check/) | 概念核验。贴身模式：一个词该不该留，三问自检 + 行业黑话豁免。深挖模式：一个模糊概念是不是没被想清楚——各说各话对齐、往回倒查原意、假设检查戳穿伪概念、检验是描述行动还是替代了行动、去词测试、判断是信息缺口还是执行缺口。 |

### 整理类

| 技能 | 干什么 |
| --- | --- |
| [organize](skills/organize/) | 深挖对话整理成稿。深挖已经做完之后，把对话里的实质内容忠实、完整地组织成正式稿件——不做精选、不设默认字数、保留追问-反驳-修正的张力，张力归属必须忠于事实，不能编成第一人称心路历程。 |

### 工作流零件类

| 技能 | 干什么 |
| --- | --- |
| [content-positioning](skills/content-positioning/) | 账号定位。锁人群 → 五种 IP 类型 → 人设 → 内容支柱（商业向 + 人设向并存）→ 承接路径。 |
| [topic-strategy](skills/topic-strategy/) | 选题策略。人性需求 × 战略意图 × 内容形式 → 八个选题口子 → 六道过滤闸 → 五类生态资产配比。 |
| [platform-distribution](skills/platform-distribution/) | 三平台适配。同一选题改出抖音 / 小红书 / 视频号三个真正不同的版本，附行业合规红线。 |

## 设计理念

1. **闸门而不是建议。** 质检不过就是不过，不写"整体不错，建议优化"。AI 最擅长的就是放水，所以规则里全是"一票否决""清单为空不许往下写"。
2. **不同类型用不同尺子。** 人设稿不挂商业承接不是缺陷，成交稿没人设也不是缺陷。拿错尺子的质检比不质检更坏。
3. **具体到能执行。** 所有结论必须落到"明天就能做的动作"，禁掉"提升信任""加强转化"这类空话。
4. **反馈要能沉淀。** 你骂过的每一句"太 AI 了"都应该变成一条可执行的长期规则，而不是下次重骂一遍。

## 安装

**不用命令行（推荐给非技术用户）**：去 [Releases 页面](https://github.com/MarchTalk/ai-content-skills/releases) 下载 zip 安装包，里面有一份三分钟装好的《安装说明.txt》（Mac / Windows 都有），解压拷贝即用。

**Claude Code（命令行）**：把 `skills/` 下你要的技能文件夹拷进 `~/.claude/skills/`（全局）或项目的 `.claude/skills/`：

```bash
git clone https://github.com/MarchTalk/ai-content-skills.git
cp -r ai-content-skills/skills/* ~/.claude/skills/
```

重启 Claude Code 后用 `/material-research`、`/quality-gate` 等方式调用，或直接说"帮我质检这条稿子"让它自动路由。

**其他 Agent（Codex 等）**：这些技能就是纯 Markdown 的流程说明书，放进任何支持技能 / 指令文件的 Agent 里都能用。

## 建议的串联方式

```
content-positioning（定位，一次性）
        ↓
topic-strategy（选题池）
        ↓
material-research B1（动笔前：查料 / 放行）★ 强制
        ↓
material-research B2（可选：命题定稿后查最强反方观点，深化判断）
        ↓
adversarial-gate mode=judgment-stress（可选：命题写正文前，压力对抗）
        ↓
（你自己的写稿流程 / 提示词，或用 organize 整理一场已经发生的深挖对话）
        ↓
quality-gate（交付前：质检）★ 强制
        ↓
adversarial-gate mode=post-draft-audit（可选：质检通过后，谄媚检测 + 结构查重）
        ↓
platform-distribution（跨平台改版）
```

两个星号的闸门是这套系统里最基础的部分：**写前有料、写后有关**。`adversarial-gate` 是再上一层——不查表达层的空话 AI 味（那是 quality-gate 的活），只管论证站不站得住、判断有没有真的被逼深，观点/认知/人设/价值观类内容用得上，成交/流量类内容可以跳过。中间的写稿流程你可以用自己的。

`concept-check` 不在这条链上，是随时能插的判断工具：写稿时纠结一个词该不该留、或者讨论中冒出一个自己都没想清楚的概念，随时调用。`buyer-psychology` 也是随时插入型：进入"为什么用户不买"的环节就调用，不绑定在固定位置。

## 这套技能不包含什么

原系统里还有写稿生成、单稿诊断、发布复盘、账号诊断等技能，因为深度绑定了具体 IP 的定位、语气指纹和客户资料，不适合开源。这里放出的是**通用零件**——方法给你，针对你自己账号的调校要你自己（和你的 AI）慢慢养出来：把每次对 AI 输出的批评和认可记下来，攒成一份你自己的长期规则文件。

## 许可证

MIT，允许商用——这是有意的：会用这套技能的人，本来就是拿它给自己的账号、自己的客户做内容的，禁了商用等于谁都不能用。方法免费送；针对具体账号的调校、语气训练和陪跑，是另一回事。

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=MarchTalk/ai-content-skills&type=Date)](https://star-history.com/#MarchTalk/ai-content-skills&Date)

---

出品：隐拾三月·AI内容系统 · [marchaihq.com](https://marchaihq.com)
