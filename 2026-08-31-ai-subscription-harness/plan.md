# Plan — 「AI订阅与Harness工具生态对比分析」PPT + 视频脚本

## 任务目标
1. 制作专业风格 PPT（主题：AI订阅与Harness工具生态对比分析），核心逻辑：「订阅必须结合自家Harness工具才能发挥实力」「买订阅 = 为了更好地用自家工具」
2. 输出配套视频讲解脚本框架（供用户照PPT录视频）

## 结构（约 22-25 页，>20页 → 必须委派子agent协作，.pptd 由主agent创建）
- 封面 + 目录（2页）
- 第一梯队：Cloud Cursor / OpenCode Go / SuperGrok / Codex+ChatGPT（约4页）
- 第二梯队：Kimi+Kimi Code / 智谱+Z Code / MiniMax / DeepSeek API / 千问Token Plan / 火山引擎 Agent+Coding Plan / Gemini AI Pro（约6-7页）
- 第三梯队：Command Code / 商汤 / 阶跃星辰 / 小米MiMo / Ollama Pro（约4-5页）
- 单独类：国内办公类Agent（腾讯WorkBuddy / 豆包 / 阿里千问办公 / 钉钉飞书企微WPS简要）（约2页）
- 总结对比表（价格/模型能力/Harness成熟度/生态闭环/适合场景）（1-2页）
- 结尾页（1页）

## Stage 1 — 研究（加载 deep-research-swarm 思路：多agent并行 + 交叉验证）
- 派 3 个并行 explore 子agent：
  - A：第一梯队4个产品（名称按用户口径，检索时对齐真实产品：Cursor、opencode、xAI SuperGrok、OpenAI Codex/ChatGPT）
  - B：第二梯队7个（Kimi Code、智谱GLM Coding Plan/Z Code、MiniMax、DeepSeek、通义千问、火山引擎、Google Gemini AI Pro）
  - C：第三梯队5个 + 办公类Agent（Claude Code/Command Code、商汤、阶跃星辰、小米MiMo、Ollama、腾讯WorkBuddy、豆包、钉钉/飞书/企微/WPS AI）
- 每个产品收集：订阅价格、绑定模型能力、配套Harness工具、生态闭环、适合场景
- 产出：研究简报 research-brief.md（当前时间 2026-08，注意时效性）

## Stage 2 — PPT 骨架（加载 kimi-slides）
- 主agent读 kimi-slides SKILL.md，确定视觉风格（专业分析风：低饱和、深色/浅色商务、对比表格友好）
- 主agent创建 .pptd 主文件 + 封面/目录/结尾页，明确风格规范写入子agent指引

## Stage 3 — 分页内容（委派子agent并行写 .page 文件）
- 子agent按梯队分工撰写各 .page，严格遵循主agent的风格规范与研究简报数据
- 每页必须体现「订阅 + 自家Harness工具」绑定分析

## Stage 4 — 组装与构建
- 主agent校验各page → 组装 .pptd → 构建 PPTX
- 校验：页数、对比表完整性、核心逻辑贯穿

## Stage 5 — 视频讲解脚本框架
- 基于最终PPT结构输出脚本框架（.md + .docx，加载 docx 技能转换）
- 逐页口播要点 + 转场提示 + 强调金句（「买订阅=买自家工具的入场券」）

## 交付物
- /mnt/agents/output/AI订阅与Harness工具生态对比分析.pptx
- /mnt/agents/output/视频讲解脚本框架.md + .docx
