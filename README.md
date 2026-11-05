# 科研写作 Skill

一个以读者理解为中心的科研写作 skill，适用于论文、学位论文章节、数学论述、方法说明，以及仿真和实验结果分析。支持中文和英文。

核心文件是 [SKILL.md](SKILL.md)。它把执行规则放在一个文件中，使用时无需访问上游网址或加载外部参考文件。

## 写作原则

1. 直接展开研究内容，减少为了预防假想质疑而插入的防御性语言。
2. 一般先给结论，紧接着解释含义，再给证明或证据。
3. 克制引入符号，用物理或数学意义及实际用途自查。
4. 使用普通而准确的名称，必要的陌生术语在首次出现时解释。
5. 在可能产生理解跳跃的地方，说明下一步为何必要、准备怎样进行。

这些原则服务于同一目标：减轻阅读负担，同时保持假设、推导、证据和引用准确。科研中的必要条件和实际限制应贴近相应结论说清。

## 使用方法

### 作为本地 Skill

在支持 `SKILL.md` 的工具中，将本仓库安装为名为 `research-writing` 的 skill。可以先克隆仓库：

```bash
git clone https://github.com/hongjinrui/writing_skills.git research-writing
```

将 `research-writing` 目录放入所用工具配置的技能目录，重新加载工具后即可使用。以支持显式调用技能的 Codex 为例：

```text
使用 $research-writing 修改下面的论文段落。保留原有数学结论和符号，
重点调整结论、解释和推导的顺序，并删去没有实际作用的防御性表述。
```

### 作为单文件指令

也可以只下载 [SKILL.md](SKILL.md)，交给支持文件指令的助手读取，并附上原稿、材料和具体任务。例如：

```text
请按附件 SKILL.md 的规则整理这一节。读者具有本科数学基础。
沿用现有符号，先说明主要结论和含义，再展开推导。
缺少依据的地方请具体标出。
```

`SKILL.md` 中已内嵌来源说明和 MIT 许可，可单文件分发。使用 skill 本身不需要读取 README 或来源仓库。

## 与参考项目的关系

本项目由 **hongjinrui** 整理，**参考并改编自 JiahaoLi-creator 的 [mathematical-academic-writing](https://github.com/JiahaoLi-creator/mathematical-academic-writing)**，再以使用者提出的五条写作要求为准重新组织、补充和改写。

对照基准为上游 v0.4.3 对应的固定提交 [`9e5eec0`](https://github.com/JiahaoLi-creator/mathematical-academic-writing/tree/9e5eec0c487a648a0311747e6f79c41bdddd5a0d)，提交日期为 2026-10-15。以下链接均固定到该版本，便于核查：

| 写作要求 | 上游已有内容 | 本项目的处理 |
| --- | --- | --- |
| 减少防御性写作 | [主文件](https://github.com/JiahaoLi-creator/mathematical-academic-writing/blob/9e5eec0c487a648a0311747e6f79c41bdddd5a0d/SKILL.md)及[防御性写作检查](https://github.com/JiahaoLi-creator/mathematical-academic-writing/blob/9e5eec0c487a648a0311747e6f79c41bdddd5a0d/references/anti_defensive_audit.md)已有明确要求。 | 按使用者的直白表述重写，保留影响结论和理解的条件，删除预防假想质疑的插话。 |
| 结论先行并解释含义 | [论文写作流程](https://github.com/JiahaoLi-creator/mathematical-academic-writing/blob/9e5eec0c487a648a0311747e6f79c41bdddd5a0d/references/research_article_workflows.md)要求结果段先给结果和依据；[文体说明](https://github.com/JiahaoLi-creator/mathematical-academic-writing/blob/9e5eec0c487a648a0311747e6f79c41bdddd5a0d/references/genre_profiles.md)已有先陈述定理、后证明的安排。 | 将“结论—解释含义—证明或证据”提升为分析段落和小节的默认顺序，强化紧接结论的解释。 |
| 克制引入符号 | [数学完整性](https://github.com/JiahaoLi-creator/mathematical-academic-writing/blob/9e5eec0c487a648a0311747e6f79c41bdddd5a0d/references/mathematical_integrity.md)要求保持符号一致，并限制新增符号。 | 补充实际用途门槛和逐个自查：说清物理意义；纯数学对象说明数学含义及作用。一次性中间量尽量直接写。 |
| 普通名称与术语解释 | 文体说明已有直接表达、需要时再引入术语等要求。 | 明确避免为包装而命名；必要的陌生术语首次出现时解释其含义和用途。 |
| 交代关键过渡 | 文体说明已有困难过渡的解释，以及非显然证明的策略提示。 | 扩展到章节、模型、方法和设计选择之间，说明与前文的联系、下一步目的和做法。 |

重合部分按使用者的要求表达；需要调整的组织规则，也以这些要求为准：

- 上游对后续内容预告和跨段复述限制较严。本项目保留能帮助理解的短预告、回顾及分工明确的主结论重述，避免重复论证。
- 上游的工作记录、核查层级等机制被精简为内部检查，只在交付需要时呈现相关问题和依据。
- 将适用的论证、引用和数值结果要求纳入单文件，省去课程、金融等专用路由以及外部文件依赖。

本项目提炼通用写作方法；原始使用场景中的具体研究课题、章节安排和仓库操作属于任务内容，不作为 skill 的固定要求。后续内容由本仓库独立维护。

## 来源与许可

本仓库以 [MIT License](LICENSE) 发布，并保留参考项目的版权和许可说明。原作者的写作框架及相关设计应归功于原作者，本项目的工作在于按上述五条要求重新组织、改写并补充执行规则。

上游的防御性写作指导还注明参考了 **Kiterlin** 的 [anti-defensive-writing](https://github.com/Kiterlin/anti-defensive-writing)。本项目保留这一间接来源的致谢及许可，详见 [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md)。

本仓库分发写作指令及项目文档。使用者应对论文中的文献、公式、数据、实验记录和署名进行核实；引用本 skill 不能替代对原始科研文献的引用。
