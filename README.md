# 四川轻化工大学计算机科学与工程学院
# 本科毕业设计（论文）LaTeX 模板 (2026 测试版)

<p align="center">
  <img src="SUSE-icon.png" width="80" alt="SUSE Logo">
</p>

<p align="center">
  <a href="#"><img src="https://img.shields.io/badge/XeLaTeX-3passes-blue?style=flat-square" alt="XeLaTeX"></a>
  <a href="#"><img src="https://img.shields.io/badge/TeXLive-2025+-green?style=flat-square" alt="TeXLive"></a>
  <a href="#"><img src="https://img.shields.io/badge/Platform-macOS%20%7C%20Windows%20%7C%20Linux-orange?style=flat-square" alt="Platform"></a>
</p>

---

## 简介

本模板根据《计算机学院-毕业设计(论文)模板(2026).doc》Word 模板**严格制作**，完整还原了论文格式要求。

**核心特性：**
- 封面、独创性声明、学术诚信声明、中英文摘要、目录、正文、致谢、参考文献、附录完整支持
- 自动适配 macOS / Windows / Linux 中文字体
- 图表编号按章分节（如 `图1-1`、`表1-1`、`式(1-1)`）
- 页眉页脚、行距、字号、段前段后间距均严格匹配 Word 模板
- 支持 7 种参考文献类型（期刊、书籍、学位论文、标准、网页、论文集、专利）

---

## 格式还原对照

| 元素 | Word 模板要求 | LaTeX 实现 | 状态 |
|---|---|---|---|
| **封面校徽** | 校徽在标题左侧，整体居中 | `\raisebox` 垂直居中对齐 | ✅ |
| **学校名称** | 小二号黑体，居中 | `\xiaoerhao\heiti` | ✅ |
| **论文题目** | 二号黑体，居中 | `\erhao\heiti\bfseries` | ✅ |
| **学生信息** | 三号黑体，居中 | `\sanhao\heiti` | ✅ |
| **学院名称** | 小二号黑体，居中 | `\xiaoerhao\heiti\bfseries` | ✅ |
| **日期** | 三号黑体，居中 | `\sanhao\heiti\bfseries` | ✅ |
| **独创性声明+授权** | 合并一页，行距22磅 | `\makedeclaration` | ✅ |
| **学术诚信声明** | 单独一页，行距28磅 | `\makeintegrity` | ✅ |
| **中文题目** | 黑体小2，段前段后12磅，行距22磅 | `\fontsize{18pt}{22pt}\heiti` | ✅ |
| **中文摘要标题** | 黑体小2，段前段后12磅 | `\xiaoerhao\heiti` | ✅ |
| **中文摘要正文** | 宋体小4，首行缩进2字符，行距22磅 | `\xiaosihao\songti` + `\parindent=2em` | ✅ |
| **英文题目** | Times New Roman 小2加粗，段前段后12磅 | `\fontsize{18pt}{22pt}\bfseries` | ✅ |
| **ABSTRACT** | Times New Roman 3号加粗，段前段后12磅 | `\sanhao\bfseries` | ✅ |
| **英文摘要正文** | Times New Roman 小4，行距22磅 | `\xiaosihao` | ✅ |
| **Keywords** | Times New Roman 小4加粗，K大写 | `\xiaosihao\bfseries Keywords:` | ✅ |
| **目录标题** | 黑体3号，段前段后12磅 | `\sanhao\heiti` | ✅ |
| **一级标题** | 黑体3号，居中，段前段后12磅 | `\chapter` 定制 | ✅ |
| **二级标题** | 黑体4号，段前段后12磅 | `\section` 定制 | ✅ |
| **三级标题** | 楷体加粗小4号，段前段后6磅 | `\subsection` 定制 | ✅ |
| **正文** | 宋体小4 / Times New Roman 小4，行距22磅 | 全局字体设置 | ✅ |
| **页眉** | 宋体五号居中（正文开始） | `\wuhao\songti` | ✅ |
| **页码** | 阿拉伯数字五号居中 | `\wuhao\thepage` | ✅ |
| **图表标题** | 五号字，表在上图在下 | `\small` + `caption` 定制 | ✅ |
| **图表编号** | 按章连续（如 `图1-1`、`表1-1`） | `\thechapter-\arabic{...}` | ✅ |
| **公式编号** | 按章连续（如 `(1-1)`） | `\thechapter-\arabic{equation}` | ✅ |
| **参考文献** | 悬挂缩进2字符，7种类型 | `thebibliography` 定制 | ✅ |
| **致谢** | 段前段后12磅，楷体 | `acknowledgements` 环境 | ✅ |
| **每章分页** | 自动分页 | `\clearpage` | ✅ |

---

## 文件结构

```
suse-cs-thesis-template/
├── suse-cs-thesis.cls      # LaTeX 类文件（格式定义核心）
├── main.tex                # 示例主文件（可直接修改使用）
├── SUSE-icon.png           # 校徽（PNG 格式）
├── main.pdf                # 编译输出示例（供参考）
├── README.md               # 本说明文件
├── chapters/               # 章节文件目录（可选，用于拆分长论文）
└── figures/                # 图片目录（可选）
```

---

## 环境要求

### 必需软件

| 软件 | 版本 | 下载 |
|---|---|---|
| **TeX Live** | 2024+ | [tug.org/texlive](https://tug.org/texlive/) |
| **MacTeX** (macOS) | 2024+ | [tug.org/mactex](https://tug.org/mactex/) |

> ⚠️ **必须使用 XeLaTeX 编译**，不支持 pdfLaTeX。

### 必需宏包

以下宏包随 TeX Live 完整版自动安装：

- `ctex` — 中文支持
- `geometry` — 页面布局
- `fancyhdr` — 页眉页脚
- `titlesec` / `titletoc` — 标题/目录格式
- `caption` — 图表标题
- `graphicx` — 图片插入
- `amsmath` — 数学公式
- `hyperref` — 超链接
- `booktabs` — 三线表

### 系统字体

模板自动检测操作系统并选择合适字体：

| 系统 | 宋体 | 黑体 | 楷体 | 仿宋 |
|---|---|---|---|---|
| **macOS** | `STSong` | `Heiti SC Medium` | `Kaiti SC` | `STSong` |
| **Windows** | `SimSun` | `SimHei` | `KaiTi` | `FangSong` |
| **Linux** | `Noto Serif CJK SC` | `Noto Sans CJK SC` | `Noto Serif CJK SC` | `Noto Sans CJK SC` |

> 💡 **macOS 用户注意**：
> - `Heiti SC` 默认匹配 Light（细体），字重过轻
> - `Hiragino Sans GB W6` 又过粗
> - 模板自动选择 `Heiti SC Medium`（中黑体），字重最接近 Word 的 `SimHei`
> - 宋体使用 `STSong` 而非 `Songti SC`，前者更接近 Word 的 `SimSun`

---

## 编译方法

### 方法 1：手动编译（推荐）

```bash
xelatex main.tex      # 第一次：生成辅助文件
xelatex main.tex      # 第二次：生成目录
xelatex main.tex      # 第三次：确保交叉引用正确
```

### 方法 2：使用 latexmk（自动编译）

```bash
latexmk -xelatex main.tex
```

编译成功后将生成 `main.pdf`。

---

## 使用指南

### 1. 修改封面信息

在 `main.tex` 导言区修改以下命令：

```latex
\thesistitle{你的论文题目}
\thesistitleen{Your English Title}
\thesisauthor{你的姓名}
\studentid{你的学号}
\major{你的专业}
\class{你的班级}
\advisor{指导教师姓名}
\thesisdate{二〇二六年五月}

% 设置校徽（支持 PNG/JPG/PDF/EPS）
\logo{SUSE-icon.png}
```

### 2. 论文结构

```latex
\begin{document}

\makecover                    % 封面
\makedeclaration              % 独创性声明 + 授权说明（一页）
\makeintegrity                % 学术诚信与 AI 使用声明

\begin{cabstract}             % 中文摘要
  ...摘要内容...
  \ckeywords{关键词1，关键词2}
\end{cabstract}

\begin{eabstract}             % 英文摘要
  ...Abstract content...
  \ekeywords{Keyword1, Keyword2}
\end{eabstract}

% 目录
\hideheader
\tableofcontents
\showheader
\clearpage

% 正文开始：固定行距22pt
\par\setlength{\baselineskip}{22pt}

% 第一章
\chapter{绪论}
\section{开发背景与意义}
\subsection{子标题}
...正文...

% 第二章
\chapter{相关技术}
...

% 结论
\chapter{结论}
...

% 致谢
\begin{acknowledgements}
  ...
\end{acknowledgements}

% 参考文献
\begin{thebibliography}{99}
  \bibitem{ref1} ...
\end{thebibliography}

% 附录
\appendix
\chapter{软件使用说明书}
...

\end{document}
```

### 3. 插入图片

```latex
\begin{figure}[htbp]
    \centering
    \includegraphics[width=0.8\textwidth]{figures/你的图片.png}
    \caption{图片标题}
    \label{fig:example}
\end{figure}
```

### 4. 插入表格

```latex
\begin{table}[htbp]
    \centering
    \caption{表格标题}
    \label{tab:example}
    \begin{tabular}{lll}
        \toprule
        列1 & 列2 & 列3 \\
        \midrule
        数据1 & 数据2 & 数据3 \\
        \bottomrule
    \end{tabular}
\end{table}
```

### 5. 插入公式

```latex
\begin{equation}
    E = mc^2
    \label{eq:emc2}
\end{equation}
```

公式编号自动按章分节，如 `(1-1)`、`(2-3)`。

### 6. 参考文献

模板支持 7 种参考文献类型，引用时使用 `\upcite{ref1}`：

```latex
\begin{thebibliography}{99}
  % 期刊
  \bibitem{ref1} 陈家琪. 运动图像处理在车型识别中的应用[J]. 汽车工程, 2005, 20(6): 33-36.
  
  % 书籍
  \bibitem{ref2} 陈家琪. C程序设计教程[M]. 北京: 新华出版社, 2004.
  
  % 学位论文
  \bibitem{ref3} 李江. 红外图像人脸识别方法研究[D]. 长沙: 国防科技大学, 2005.
  
  % 电子文献
  \bibitem{ref4} 王明亮. 关于中国学术期刊标准化数据库系统工程的进展[EB/OL]. 1998-08-08. http://www.example.com.
  
  % 论文集
  \bibitem{ref5} 汪学军. 中国农业转基因生物研发进展与安全管理[C]//... 2002: 22-25.
  
  % 专利
  \bibitem{ref6} 刘官山. 一种大数据学习系统: CN202210129842.1[P]. 2022-05-13.
\end{thebibliography}
```

---

## 页码格式

| 页面 | 页码格式 |
|---|---|
| 封面 | 无页码 |
| 独创性声明 + 授权说明 | 无页码 |
| 学术诚信声明 | 无页码 |
| 中文摘要 | 阿拉伯数字，从 **1** 开始 |
| 英文摘要 | 阿拉伯数字，继续 |
| 目录 | 阿拉伯数字，继续 |
| 正文 | 阿拉伯数字，继续 |
| 致谢 | 阿拉伯数字，继续 |
| 参考文献 | 阿拉伯数字，继续 |
| 附录 | 阿拉伯数字，继续 |

---

## 注意事项

### 关于行距

模板在 `ctexbook` 基础上精确控制行距：

| 区域 | 行距 | 实现方式 |
|---|---|---|
| 正文、摘要、目录 | 22pt | `\setlength{\baselineskip}{22pt}` |
| 学术诚信声明 | 28pt | `\setlength{\baselineskip}{28pt}`（仅在 `\makeintegrity` 内） |
| 创新性声明 | 22pt | `\par\setlength{\baselineskip}{22pt}` |

> ⚠️ `ctexbook` 默认启用 `linespread` 放大机制，直接使用 `\fontsize{12pt}{22pt}\selectfont` 会得到约 28.6pt 的行距。模板已处理此问题，用户无需额外设置。

### 关于字体

- 模板已自动检测系统字体，**无需手动修改**
- 如需强制指定字体，编辑 `suse-cs-thesis.cls` 中字体设置部分

### 关于目录跨页

模板已优化目录格式。若论文章节较多导致目录跨页，第二页可能显示页眉，这不影响论文整体格式。

### 关于参考文献数量

- 设计类题目：不少于 20 篇
- 论文类题目：不少于 30 篇
- 至少含 2 篇英文文献
- 尽量引用最近 3 年的文献

---

## 常见问题

### Q: 编译报错 "Font not found"？

**A**: 确保系统安装了中文字体：
- **macOS**: `STSong`、`Heiti SC Medium`、`Kaiti SC`（系统自带）
- **Windows**: `SimSun`、`SimHei`、`KaiTi`（系统自带）
- **Linux**: 安装 `fonts-noto-cjk` 包

### Q: 如何修改页边距？

**A**: 在 `suse-cs-thesis.cls` 中修改 `geometry` 参数，默认已匹配 Word 模板（上/下 2.54cm，左 3.17cm，右 3.17cm）。

### Q: 章节标题显示为数字而非"第一章"？

**A**: 确保使用 **XeLaTeX** 编译，不要使用 pdfLaTeX。

### Q: 参考文献想用 BibTeX/BibLaTeX？

**A**: 将 `thebibliography` 环境替换为 `\bibliography{references}`，配合 `.bib` 文件使用。注意需自行调整引用格式以匹配模板要求。

### Q: 如何添加更多章节？

**A**: 在 `main.tex` 中继续添加 `\chapter{章节标题}` 即可，每章自动分页。

---

## 更新日志

### v2.0 (2026-05-20)
- 严格按 Word 模板修复全部格式
- 修复封面校徽垂直居中位置
- 独创性声明合并为一页，添加学术诚信声明
- 修复中英文摘要标题和正文字号、行距
- 修复页眉页脚格式
- 修复图表前后间距
- 修复公式编号格式
- 修复参考文献悬挂缩进
- 添加 7 种参考文献类型示例
- 修复 `ctexbook` 行距放大导致的 baselineskip 问题

### v1.0 (2026-05-20)
- 初版发布

---

## 许可

本模板仅供四川轻化工大学计算机科学与工程学院学生撰写本科毕业设计（论文）使用。

---

<p align="center">
  四川轻化工大学计算机科学与工程学院
</p>
