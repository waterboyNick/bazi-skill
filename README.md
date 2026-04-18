# bazi-skill

一个面向现代中文表达的八字解读仓库。

这个仓库包含两部分：

- `skill/bazi-reading/`
  面向 Codex / 支持 `SKILL.md` 的 agent 的八字 skill
- `prompts/`
  面向普通聊天模型的可复制 prompt 套件

目标不是做“玄之又玄”的神棍话术，而是保留八字、四柱、大运、流年的框架，同时把判断翻译成现代、直接、具体的人话。

## 仓库内容

- `skill/bazi-reading/SKILL.md`
  skill 主规则，定义触发条件、输出顺序、语气、时间线优先级、断事方式
- `skill/bazi-reading/references/bazi-reference.md`
  八字术语、十神、五行、事件翻译模板、现代白话对照
- `skill/bazi-reading/agents/openai.yaml`
  skill 的 UI 元数据
- `prompts/full-prompt.md`
  适合上下文更强模型的完整版 prompt
- `prompts/lite-prompt.md`
  适合免费模型、短上下文模型的轻量版 prompt
- `prompts/two-step-prompts.md`
  适合容易忘规则的模型，先出底稿再正式解读
- `prompts/user-template.txt`
  给普通用户直接填写出生信息或四柱

## 适合谁用

- 想在 Codex 或其他 agent 里直接调用八字 skill 的人
- 想在豆包、DeepSeek、Kimi、ChatGPT 等普通聊天模型里复制 prompt 使用的人
- 想把八字表达方式从传统术语腔改成现代说明文风的人

## 使用方式

### 1. 在支持 skill 的 agent 里用

把 `skill/bazi-reading/` 放到技能目录，然后显式调用：

```text
用 $bazi-reading 给我做完整断事。
```

### 2. 在普通聊天模型里用

优先从 `prompts/full-prompt.md` 开始。

如果模型容易跑偏、忘规则或输出太短：

- 改试 `prompts/lite-prompt.md`
- 还不稳的话，用 `prompts/two-step-prompts.md`

## 设计方向

这套规则默认强调：

- 先讲整体命势，再讲过去应事和未来几年
- 每个判断都尽量落到现实事件层
- 术语第一次出现就翻译成人话
- 少用宿命腔，多用模式和机制解释
- 不靠“说半句”制造神秘感

## 提醒

这是传统命理框架下的娱乐向、象意式解读，不是科学预测，也不应用来替代医学、法律、投资等高风险判断。
