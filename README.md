# 西南交通大学 Beamer 模板

本目录是面向西南交通大学科研汇报的 LaTeX Beamer 模板。模板保留了原主题的页眉、页脚、目录、标题页和常用区块布局，但已将校徽、校楼、验证图片和主题包名称整理为 SWJTU 版本。

## 主要文件

- `main.tex`：可直接复制修改的中文主示例。
- `beamerthemeswjtu.sty`：主主题包。
- `beamercolorthemeswjtu.sty`：颜色主题。
- `beamerinnerthemeswjtu.sty`：内部主题。
- `beamerouterthemeswjtu.sty`：外部主题。
- `resources/`：西南交通大学校徽、校楼、验证图片和背景资源。

## 编译

默认示例使用 XeLaTeX 编译：

```bash
xelatex -interaction=nonstopmode main.tex
```

如果需要参考文献，将 `main.tex` 中的 `BIBMode=none` 改为 `BIBMode=biber`，并使用 XeLaTeX + Biber 完成编译。

请保持源文件为 UTF-8 编码，并在编译时保留整个模板目录，以便主题包和资源文件能够被找到。
