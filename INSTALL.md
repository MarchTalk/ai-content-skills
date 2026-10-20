# 九方法安装说明 · v1.2.0

这是给 AI 助手读取的本地工作说明，不是网页插件，也不包含自动安装程序。先安装一个 `quality-gate`，确认能被识别，再按需要添加其他方法。

## 1. 确认下载的是当前九方法

下载 [v1.2.0](https://github.com/MarchTalk/ai-content-skills/releases/tag/v1.2.0) 的 `ai-content-skills-v1.2.0.zip` 并解压。打开 `ai-content-skills/skills/`，应当恰好看到：

1. `content-positioning` · 定位
2. `topic-strategy` · 选题策略
3. `material-research` · 实料调研
4. `buyer-psychology` · 商业心理
5. `organize` · 整理成稿
6. `platform-distribution` · 平台适配
7. `quality-gate` · 发布前检查
8. `adversarial-gate` · 压力对抗
9. `concept-check` · 概念核验

每个文件夹内有一份 `SKILL.md`。v1.0／v1.1 是不同组合的历史版本，不需要为安装新版删除它们；不要混用旧包中的清单。新版九份正文与打包时仓库的当前文件相同，包内 `MANIFEST.json` 记录来源和校验值。

## 2. 选择一个本地安装位置

以下路径用于本地 Codex／Claude Code 的技能发现。请先安装相应客户端并打开自己的项目；这份说明不代替它们的账号、客户端或云端设置。

推荐先放在项目里，方便知道它影响哪个项目：

| 客户端 | 放在自己的项目中 | 安装后的例子 |
| --- | --- | --- |
| Codex | `.agents/skills/` | `你的项目/.agents/skills/quality-gate/SKILL.md` |
| Claude Code | `.claude/skills/` | `你的项目/.claude/skills/quality-gate/SKILL.md` |

需要跨项目使用时，可选择个人目录：

| 客户端 | Mac／Linux | Windows |
| --- | --- | --- |
| Codex | `~/.agents/skills/` | `%USERPROFILE%\.agents\skills\` |
| Claude Code | `~/.claude/skills/` | `%USERPROFILE%\.claude\skills\` |

`~` 指自己的用户主目录；Mac 可在访达“前往文件夹”中输入路径，Windows 可在文件资源管理器地址栏输入对应路径。目标文件夹不存在时先创建。

从解压包的 `skills/` 中复制需要的整个技能文件夹，例如 `quality-gate/`，不要只复制 `SKILL.md`，也不要再套一层 `skills/skills/`。项目和个人目录先选一个，避免无意保留两份同名技能。

如果目标已有同名文件夹，先另存备份、比较自己的修改，再决定是否替换；不要直接覆盖或把新旧文件混在一起。此安装包不会自动删除历史技能，也不会修改客户端配置。

## 3. 先确认识别，再试一段自己的稿子

在选定项目的新会话中，让助手列出可用 Skill，确认包含 `quality-gate`。Codex 没有显示新技能时可重启后再看；Claude Code 也可用技能列表检查是否已加载。

再提供一段你自己的原稿、给谁看和想达到什么目的，请它按 `quality-gate` 检查。Codex CLI／IDE 可用 `$` 选择技能；Claude Code 可输入 `/quality-gate`。不同客户端界面可能不同，以其当前技能选择界面为准。

能看到名称只代表被发现；还要检查它是否读取了这份技能、按原稿指出了具体句子的问题。不要把一段泛泛的“整体不错”当作已经验证成功。技能调用也不保证事实正确或平台一定允许发布，仍需本人核对。

## 4. 没识别时先查三处

- 是否打开了放置项目技能的那个项目，或使用了对应个人目录。
- 路径是否为 `<技能名>/SKILL.md`，没有多套一层目录，文件名大小写正确。
- 是否有同名技能、组织设置或客户端限制。不要反复覆盖文件；先查当前客户端官方说明。

联网调研需要助手具备相应工具；压力对抗需要支持独立上下文／子代理的环境。没有对应能力时，应明确说明限制，不要把普通单次回答称作已完成该流程。

原稿会由你选用的 AI 助手处理。请按该产品的隐私与权限设置决定是否提供客户资料，不因“本地文件安装”而假定稿件不会离开设备。

## 官方说明与本次核对范围

- [OpenAI：本地技能位置与使用](https://learn.chatgpt.com/docs/build-skills#where-codex-loads-local-skills)
- [Claude Code：技能加载位置](https://code.claude.com/docs/en/skills#choose-where-skills-load)

路径与调用说明于2026-10-20对照以上官方文档核对。本次发行验证的是九文件一致性、安装目录结构、归档与校验值；没有对所有客户端版本、云端环境或真实写稿效果作保证。
