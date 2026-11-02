# Lab Report Skill｜中文实验报告编写与排版

把实验思路、关键代码、真实结果和 Word 排版整理到同一套工作流程里。

`lab-report` 是面向 Codex 的中文课程实验报告 Skill，适合计算机、软件工程及相关课程。它根据教师模板、实验要求、代码、截图与日志，辅助编写正文、整理 DOCX、制作实验总览图，并在明确要求时打包最终提交文件。

它来自实际报告整理中积累的规则，重点是 **保留模板、解释原理、核对证据和检查版面**。本仓库提供技能指令与参考规范，不包含自动运行的报告生成程序，也不承诺成绩或一次生成即可提交。

[阅读技能](lab-report/SKILL.md) · [排版规范](lab-report/references/formatting-standard.md) · [写作示例](lab-report/examples/good-report-example.md) · [MIT 许可证](LICENSE)

## 能做什么

| 任务 | 处理方式 |
| --- | --- |
| 整理已有报告 | 在副本中局部编辑，保留教师模板的结构、表格和固定区域 |
| 编写或补全正文 | 结合真实材料说明目标、原理、关键实现及结果验证 |
| 分析关键代码 | 节选实际源码，解释设计理由、输入输出及与原理的对应关系 |
| 制作实验总览图 | 按实验关系选择流程、结构、数据通路或状态变化图，优先交付可编辑 VSDX |
| 整理实验截图 | 核对来源、上下文、图题和最终阅读尺寸下的清晰度；有可用工具时采集真实窗口 |
| 打包提交材料 | 按要求整理最终报告、核心代码与必要资源，保持运行所需目录结构 |

## 默认规则

- **教师模板优先，明确的用户要求可以覆盖默认规则。** 封面、姓名学号、教师批阅、成绩、签字及评审区默认由使用者手动处理。
- **仅排版不自动扩写。** 只修改指定段落、只插图或只打包时，保持任务范围。
- **实验事实必须有依据。** 不虚构运行结果、截图、测量值、故障经历或测试通过情况；材料不足时留下明确待补项。
- **图和代码要帮助解释实验。** 总览图不替代正文推理，代码节选不替代原理分析，单张截图不证明整体成功率。
- **检查最终 DOCX。** 有可用渲染工具时检查分页、裁切、图题分离和可读性；无法完成的验证应单独说明。

本 Skill 保留了维护者的个人格式预设，例如正文宋体五号、顶层标题宋体四号加粗，以及独立代码块四汉字格左缩进、Times New Roman。文中“用户已确认”指维护者在原始使用过程中的历史选择，不代表学校统一规范或其他使用者的历史授权。请按本次课程和自己的明确要求覆盖这些预设，具体参数见[排版规范](lab-report/references/formatting-standard.md)。

## 安装

### 方式一：让 Codex 安装

在支持 `$skill-installer` 的 Codex 环境中发送：

```text
$skill-installer 请从 https://github.com/Tcskywttc/lab-report-skill
安装 lab-report 目录中的技能。若已安装同名技能，先比较差异，不要直接覆盖我的定制版本。
```

### 方式二：手动安装

1. 点击仓库的 **Code → Download ZIP**，下载并解压。
2. 将里面的 **`lab-report` 文件夹**放入个人技能目录。
3. 确认 `SKILL.md` 直接位于 `lab-report/` 下，不要多套一层同名目录。

按 [OpenAI 官方技能文档](https://learn.chatgpt.com/docs/build-skills)，本地个人技能目录为：

| 系统 | 目标文件位置 |
| --- | --- |
| Windows | `%USERPROFILE%\.agents\skills\lab-report\SKILL.md` |
| macOS / Linux | `~/.agents/skills/lab-report/SKILL.md` |
| 仅当前项目使用 | `<项目根目录>/.agents/skills/lab-report/SKILL.md` |

如果现有环境通过安装器使用其他技能目录，以该环境实际识别的目录为准；避免在多个目录重复安装同名技能。未显示新技能时，重启客户端后再检查。

## 怎么使用

先提供实验要求、教师模板或待修改报告，再提供与本次实验对应的代码、日志、数据和截图。原稿中已有的截图无需重复提供；有多份报告时，请标明以哪份为准。封面个人信息不需要为使用本技能另行提供。

### 补全报告正文

```text
$lab-report 请根据本次实验材料补全报告正文并交付 DOCX 副本。

实验要求：见附件“实验要求.pdf”
待修改报告：见附件“实验报告.docx”，以这一份为准
代码与结果：见附件“实验材料”目录
需要补充：原理、关键代码分析、结果验证和结论
总览图：放在方法步骤前部，制作可编辑 Visio 图
保护区域：封面和教师评审区域保持原样
材料不足：列出待补证据，不编造结果
```

### 只调整格式

```text
$lab-report 只整理这份报告的正文排版，保留原文与实验事实。
不要扩写或新增总览图；封面和教师评审区域保持原样。
输出 DOCX 副本，并说明实际完成的版面检查。
```

### 打包最终提交文件

```text
$lab-report 请以我刚手工修改的“实验报告_最终版.docx”为准，
将报告与程序运行必需的代码、配置及资源一起打包为 ZIP。
保留相对目录结构，不修改报告内容。
按实验提交要求命名；没有特殊要求时，ZIP 与最终报告同名。
```

也可以在技能选择器中选中 `lab-report` 后直接描述任务。具体的技能调用界面因客户端而异。

## Visio 配色与构图样例

仓库单独提供软件工程 exp3 的三页可编辑视觉样例，以及从实际 VSDX 提取的配色、字号、线宽和布局说明：

- [下载可编辑 Visio 样例](lab-report/assets/visio-exp3/exp3-flowchart-reference.vsdx)
- [查看完整分析与迁移规则](lab-report/references/visio-exp3-design.md)
- [算法全景](lab-report/assets/visio-exp3/01-overview.svg)、[完整控制流](lab-report/assets/visio-exp3/02-control-flow.svg)、[进位机制](lab-report/assets/visio-exp3/03-carry-mechanism.svg)矢量预览

![exp3 算法全景配色与布局](lab-report/assets/visio-exp3/01-overview.png)

新图默认借鉴“浅色职责分区 + 深色标题与描边”的蓝、青绿、琥珀、紫配色，以及阶段总览、职责分栏、状态局部展开三种构图。按内容选用，不要求每次四色或三张图。规则同时要求检查最终入稿字号和回路连线。

该文件是含原实验内容的 `.vsdx` 参考样例，不是空白 `.vstx` 模板。个人作者元数据已去除，原生形状与文字保留；部分连接采用手工折线，移动节点后须重接或核对。样例算法与数值不作为其他实验的结果证据。

## 环境与交付

Skill 本身是 Markdown 与 YAML 文件；实际编辑、渲染、截图和绘图取决于运行它的智能体及可用工具。

| 工作 | 所需能力与交付边界 |
| --- | --- |
| DOCX 编辑与验收 | 需要文档编辑与渲染工具；字体或渲染器缺失时应说明限制 |
| Visio 绘图 | 优先使用已安装的 Microsoft Visio；Windows COM 自动化需要本机环境支持 |
| 无 Visio 的环境 | 未限定 Visio 时可用可编辑 SVG 等替代；明确要求 VSDX 时应保留为未完成项 |
| 自动截图 | 需要当前环境支持的电脑操作或截图工具，以及可访问的真实实验窗口 |
| 打包与运行验证 | 需要文件访问与压缩工具；测试范围由运行环境和任务授权决定 |

普通报告任务交付 DOCX 副本；制作流程图时同时交付源图与实际使用的导出图。明确要求打包时再生成 ZIP。制作附件不默认全部装入最终提交包，具体见[打包规则](lab-report/SKILL.md#最终提交打包)。

## 仓库结构

```text
lab-report-skill/
├── README.md
├── LICENSE
├── .gitignore
└── lab-report/
    ├── SKILL.md
    ├── agents/
    │   └── openai.yaml
    ├── assets/
    │   └── visio-exp3/                  # VSDX 与三页 SVG / PNG
    ├── examples/
    │   └── good-report-example.md
    └── references/
        ├── docx-template-rule.md
        ├── evidence-rule.md
        ├── flowchart-guide.md
        ├── formatting-standard.md
        ├── report-structure.md
        ├── screenshot-guide.md
        ├── visio-exp3-design.md
        └── writing-guideline.md
```

仓库仅附带上述脱敏 Visio 视觉样例，未附带完整学生报告、学校教师模板、个人截图、真实实验数据或软件安装包。写作和图形示例用于说明组织方法，不能作为新实验的证据。

## 反馈与改进

欢迎通过 [Issues](https://github.com/Tcskywttc/lab-report-skill/issues) 或 Pull Request 反馈。描述任务类型、预期行为、实际问题和使用环境即可；需要复现材料时，请先脱敏并确认有权公开，尤其注意姓名、学号、成绩、账号、路径和截图中的个人信息。

优先欢迎能复现的问题，例如局部编辑扩大了修改范围、保护区域发生变化、图文不同步、代码换行破坏含义或打包漏掉依赖。

## 参考与许可

开源仓库的介绍与使用说明组织方式参考了 [hanyu0510/SZU-CS-high-score-lab-report-skill](https://github.com/hanyu0510/SZU-CS-high-score-lab-report-skill)。本仓库发布的是维护者已有的 `lab-report` 技能，没有复制该仓库的报告图片或模板。

本项目采用 [MIT License](LICENSE)。本项目是个人维护的实验报告工作流，不代表学校或课程官方要求。使用时请遵循本课程关于独立完成实验、材料使用和 AI 辅助披露的规定。
