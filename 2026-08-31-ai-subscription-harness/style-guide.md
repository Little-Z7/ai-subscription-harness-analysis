# 风格规范 — AI订阅与Harness工具生态对比分析（子agent必读）

## 项目结构
- 主文件：`/mnt/agents/output/ai-subscription-harness/ai-subscription-harness.pptd`（已存在，禁止修改）
- 你的任务：在 `/mnt/agents/output/ai-subscription-harness/pages/` 下写指定的 `.page` 文件
- 页面尺寸 960×540，坐标原点左上角，单位 px

## 主题 token（用 $ 引用，已定义在 .pptd）
- 颜色：`$primary`(#1C3D5A 深墨蓝) `$primaryMid`(#3E6486) `$primarySoft`(#7A99B5) `$tint`(#EDF2F7) `$accent`(#B07D3A 铜色) `$accentSoft`(#F0E6D6) `$ink`(#1F2933 正文) `$gray`(#5C6B7A) `$faint`(#97A5B2) `$hairline`(#D5DDE5)
- 文字样式：`$kicker` `$nav` `$pageTitle` `$pageSub` `$h2` `$body` `$small` `$source`
- 表格样式：`$default`（深蓝表头白字、细横线、无竖线、首列加粗）
- 标题字体已内置：思源宋体(中文衬线)+Oranienbaum(英文衬线)；正文 MiSans+Liter

## 铁律（analysis-decision 咨询风）
1. 白底、无阴影、无渐变、无圆角卡片、无彩色堆砌；只用线条/留白/字号层级
2. 每页主标题是一句「声明式结论」（完整判断句），不是名词短语
3. 所有事实/价格数据必须带来源：页脚 Source 行用 <a href="url"> 超链接标注
4. 禁止编造数据；研究简报中没有的信息宁可不写
5. 每页必须体现核心逻辑：「订阅 × 自家Harness工具 = 真实战力」

## 内容页统一骨架（坐标必须精确复用）
```yaml
pageType: content
background: {type: solid, color: "#FFFFFF"}
elements:
  # kicker（左上角章节标签）
  - {elementId: kicker, elementType: text, bounds: [48, 26, 420, 14], content: {style: "$kicker", wrap: false, align: [left, middle], text: "TIER 1 · 第一梯队"}}
  # 章节导航（右上角，当前章节用 $primaryMid 加粗，其余默认 $faint）
  - elementId: nav
    elementType: text
    bounds: [480, 24, 432, 14]
    content:
      style: "$nav"
      wrap: false
      align: [right, middle]
      text: |
        <p>核心框架 · <span style="color:$primaryMid"><strong>第一梯队</strong></span> · 第二梯队 · 第三梯队 · 办公Agent · 总结</p>
  # 主标题（声明式结论句）
  - {elementId: title, elementType: text, bounds: [48, 46, 864, 32], content: {style: "$pageTitle", wrap: false, align: [left, middle], text: "……"}}
  # 结论副标题
  - {elementId: subtitle, elementType: text, bounds: [48, 82, 864, 17], content: {style: "$pageSub", wrap: false, align: [left, middle], text: "……"}}
  # 标题区装饰：主色短棒 + 细横线
  - {elementId: titlebar, elementType: shape, bounds: [48, 106, 56, 3], shapeName: rect, fill: {type: solid, color: "$primary"}}
  - {elementId: titleline, elementType: shape, bounds: [48, 111, 864, 0.75], shapeName: rect, fill: {type: solid, color: "$hairline"}}
  # …… 内容区 y 122 ~ 496 ……
  # 页脚
  - elementId: source
    elementType: text
    bounds: [48, 512, 740, 12]
    content:
      style: "$source"
      wrap: false
      align: [left, middle]
      text: |
        <p>Source: <a href="https://...">官网定价页</a>（2026-08）…</p>
  - {elementId: pagenum, elementType: text, bounds: [860, 512, 52, 12], content: {style: "$source", wrap: false, align: [right, middle], text: "06 / 24"}}
```
注意：导航中当前章节名要替换成你负责页面对应的章节；页码按文件编号（01_cover=01, 06_t1_cursor=06 …）。

## 产品页版式（06-09、11-17、19 必须严格套用）
- 左栏 x=48 w=300：
  - `[48,124,300,26]` 产品名 20px bold $primary（fontFamily: {latin: "Liter", ea: "MiSans"}）+ 厂商定位（同一文本框第二行 small）
  - `[48,184,300,15]` h2「订阅档位与价格」
  - `[48,204,300,~140]` 表格 elementType: table, style: "$default"，列如 [档位, 价格, 要点]，columnWidths 按需，rowHeights 均分
  - `[48,360,300,15]` h2「独特卖点与短板」
  - `[48,380,300,~64]` small 文本（卖点1行+短板1行）
- 右栏 x=376 w=536（三个信息块，块间以 0.75px $hairline 细线分隔，线宽536）：
  - 块1 `[376,124]`：h2「模型能力」+ `[376,144,536,~64]` body
  - 分隔线 `[376,~216,536,0.75]`
  - 块2 `[376,~228]`：h2「配套 Harness 工具」+ 成熟度评级（●●●●○ 字符，$accent 色）+ body
  - 分隔线 `[376,~316,536,0.75]`
  - 块3 `[376,~328]`：h2「生态闭环与适合场景」+ body（至 y~432）
- 底部「订阅×工具」绑定点评条（每页必带，全报告的记忆点）：
  - accent 竖棒 `[48,446,4,42]`
  - 标签 `[64,446,220,13]`：10px bold $accent「订阅 × 工具 绑定逻辑」
  - 点评 `[64,462,848,28]`：body 11px，一句犀利结论（为什么买这个订阅=为了用好这个工具）
- 右栏三个块的高度可按内容微调 ±8px，但 x/宽/分隔线位置不动

## 章节页（divider）版式参考 pages/05_t1_divider.page，复制后改编号/标题/清单即可

## pptd 语法要点
- YAML 1.2；文本含 `:` `#` 时必须用 block scalar（`text: |` 另起一行缩进书写）
- 单行文本加 `wrap: false`；多行用 `<p>` 分段
- 富文本：`<strong>` `<span style="color:$accent">` `<a href="">`；`<p style="margin-top:6px">` 控制段距
- elementId 同页唯一；elementType: text/shape/line/image/icon/table/chart
- icon 用 Font Awesome：`iconName: "fas:xxx"`，`fill: {type: solid, color: "$primary"}`
- bounds 不许超出 [960,540]；写完自检文字是否溢出（11px 字一行约 78 个英文字符 / 39 个中文字符，栏宽 536px）
