# AI 内容技能集 · Content Creation Skills

> 一套给 AI 编程助手（Claude Code / Codex 等）用的中文内容创作技能，来自「隐拾三月·AI内容系统」的实战沉淀。
>
> A set of Chinese content-creation skills for AI coding agents (Claude Code, Codex, etc.), extracted from a working one-person content production system.

这不是提示词合集，是一套**带质检闸门的内容工作流零件**。每个技能都有明确的调用时机、工作步骤、输出格式和质检标准，AI 跑完能自查有没有做到位。

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
| [material-research](skills/material-research/) | **实料调研闸门**。动笔前强制跑：干货型必须联网查到真实案例 / 数字 / 一手细节，列"实料清单"，清单为空不许写；观点型显式放行。判据只有一条：删掉这条料，稿子会不会塌。 |
| [quality-gate](skills/quality-gate/) | **最终质检闸门**。九条通用质检（空话 / 模板腔 / AI 腔 / 机械排比 / 书面词…）+ 按内容类型分清单质检 + AI 味一票否决 + 平台合规一票否决。不放水。 |
| [feedback-capture](skills/feedback-capture/) | **反馈沉淀机制**。把你对 AI 的每次批评（和认可）提炼成结构化的长期规则，只在你明确说"记下来"时入档，只追加不覆盖。让 AI 不再重复挨同一顿骂。 |

### 底层判断类

| 技能 | 干什么 |
| --- | --- |
| [business-thinking](skills/business-thinking/) | 商业思维。真伪需求 → 产品翻译 → 六类购买阻力 → 内容角色 → 商业落点。落点必须是明天就能做的具体动作。 |
| [human-psychology-game](skills/human-psychology-game/) | 用户心理。七类心理状态 → 还原"不会说出口的内心独白" → 六种锚点 → 落到一句具体的话。 |

### 工作流零件类

| 技能 | 干什么 |
| --- | --- |
| [content-positioning](skills/content-positioning/) | 账号定位。锁人群 → 五种 IP 类型 → 人设 → 内容支柱（商业向 + 人设向并存）→ 承接路径。 |
| [topic-strategy](skills/topic-strategy/) | 选题策略。人性需求 × 战略意图 × 内容形式 → 八个选题口子 → 六道过滤闸 → 五类生态资产配比。 |
| [platform-distribution](skills/platform-distribution/) | 三平台适配。同一选题改出抖音 / 小红书 / 视频号三个真正不同的版本，附行业合规红线。 |
| [visual-aesthetic](skills/visual-aesthetic/) | 视觉审美。场景 → 调性 → 信息分层 → 画面结构 → 字体色彩 → 手机端可读性 → 禁区核查。 |

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
material-research（动笔前：查料 / 放行）★ 强制
        ↓
（你自己的写稿流程 / 提示词）
        ↓
quality-gate（交付前：质检）★ 强制
        ↓
platform-distribution（跨平台改版）
        ↓
feedback-capture（人工反馈后：沉淀规则）
```

两个星号的闸门是这套系统里最值钱的部分：**写前有料、写后有关**。中间的写稿流程你可以用自己的。

## 这套技能不包含什么

原系统里还有写稿生成、单稿诊断、发布复盘、账号诊断等技能，因为深度绑定了具体 IP 的定位、语气指纹和客户资料，不适合开源。这里放出的是**通用零件**——方法给你，针对你自己账号的调校要你自己（和你的 AI）用 `feedback-capture` 慢慢养出来。

## 许可证

MIT，允许商用——这是有意的：会用这套技能的人，本来就是拿它给自己的账号、自己的客户做内容的，禁了商用等于谁都不能用。方法免费送；针对具体账号的调校、语气训练和陪跑，是另一回事。

---

出品：隐拾三月·AI内容系统 · [marchaihq.com](https://marchaihq.com)
