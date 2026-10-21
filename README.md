# 西南交通大学 Beamer 科研汇报主题

保留 SWJTU 蓝色视觉体系，普通内容通过原生 LaTeX 编排。无需把整页内容制作成图片。

## 文件与用途

- main.tex：新版科研汇报示例，包含纯文字、TikZ 示意图、频域运动方程、PGFPlots 曲线、大图侧栏、左右对照、三线表与结论。
- examples/legacy-showcase.tex：完整备份原先的卡片式示例。
- beamerthemeswjtu.sty：主题与轻量内容组件。
- beamerstyleswjtu.sty：画幅、字重、字号、行距。
- beamerautolayout.sty：可选的简单文本网格，默认输出无卡片外框的文字。
- tests/layout-smoke.tex：组件回归编译示例。

## 编译

使用较新的 TeX Live，XeLaTeX 编译两遍以更新目录：

    xelatex -interaction=nonstopmode -halt-on-error main.tex
    xelatex -interaction=nonstopmode -halt-on-error main.tex

或：

    latexmk -xelatex -interaction=nonstopmode -halt-on-error main.tex

项目内置 Noto Sans SC 字体。默认 CodeDisplay=listing，无需 Python/Pygments 或 shell-escape，使用 minted 时需要额外安装配置。请保留 fonts/ 和 resources/ 目录。

## 最简内容写法

    \begin{frame}[t]{浮体响应分析}
      \ResearchLead{展示本页核心观点}
      \begin{columns}[T,onlytextwidth]
        \begin{column}{.64\textwidth}
          \[ H(\omega)=\frac{\hat{\xi}(\omega)}{a} \]
        \end{column}
        \begin{column}{.32\textwidth}
          \ResearchHeading{解释}
          补充变量定义与物理意义。
        \end{column}
      \end{columns}
    \end{frame}

## 推荐接口

- ResearchLead：页内核心观点，以大号蓝色文字呈现。
- ResearchHeading：普通内容小节标题。
- ResearchNote：可选的浅蓝背景与细左边线，只强调重点。
- ResearchCard：与旧稿兼容，保留简单外框，整数参数如 [1] 不再渲染圆形编号。
- autolayout / autoblock：适用于简单短文本的网格布局。因旧版布局使用启发式宽高测量并重复执行内容，复杂公式、计数器、TikZ、PGFPlots、表格和代码请优先采用显式 columns 布局。

## 视觉参数

- beamercolorthemeswjtu.sty：PrimaryC、AuxiliaryC、NormalTextC 等颜色。
- beamerstyleswjtu.sty：统一的字号与行距配置；正文为 Noto Sans SC Regular，标题用 Bold。
- SectionTOC=hide：默认不自动在每一章插入目录页；需要时设置 SectionTOC=show。
- Miniframes=none：不显示顶部迷你帧。

一页展示一个主问题、一项主要证据或一条核心结论；让公式、曲线和模型优先使用主要版面。main.tex 的示意曲线和科研内容仅用于排版与功能演示，应替换为实际科研数据与结果。
