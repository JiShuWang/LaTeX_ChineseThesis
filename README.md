# LaTeX_ChineseThesis
一个用于中文研究生学位论文撰写的LaTeX模板及其基本使用教程。该模板最初是用于云南大学研究生学位论文的撰写，但国内的学位论文格式基本一致，因此也可扩展到各个高校的研究生学位论文撰写。

## 1.论文编写环境配置
在线工具：推荐Overleaf，支持在线、多人协作等功能，同时不用配置环境，但最近由于编译时长的缩短，大篇幅的学位论文很难通过编译。
本地部署（也是本教程中所采用的方案）：首先安装TeX Live，然后使用VSCode作为编写工具，并在VSCode中安装LaTeX和LaTeX Workshop这两个插件。后续的论文撰写将严格依赖于插件的配置。具体流程请参阅：https://github.com/James-Yu/LaTeX-Workshop/wiki/Install。

## 2.注意事项
由于默认的LaTeX环境使用latex编译器，而该编译器不支持中文论文的编译，所以需要修改默认（首选）的编译器。同时由于LaTeX编译后会自动生成一些文件，还需要自动完成对这些文件的清理。此外，还有一些其它的配置项（如是否用浏览器打开编译后的pdf文件）需要根据需求自行配置，所以提供以下的配置模板，直接将该模板复制，然后找到LaTeX Workshop中的settings.json文件（或者在settings中查找recipes并编辑该文件），将该模板粘贴即可。
{
    // latex 配置
    // "latex-workshop.view.pdf.viewer": "browser",
    // "latex-workshop.view.pdf.ref.viewer": "auto",
    // "latex-workshop.view.pdf.external.viewer.args": [
    //     "%PDF%"
    // ],
    "latex-workshop.latex.tools": [
        {
            "name": "xelatex-latexmk",
            "command": "latexmk",
            "args": [
                "-f",
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "-xelatex",
                "-outdir=%OUTDIR%",
                "%DOC%"
            ]
        },
        {
            "name": "pdflatex-latexmk",
            "command": "latexmk",
            "args": [
                "-f",
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "-pdf",
                "-outdir=%OUTDIR%",
                "%DOC%"
            ]
        },
        {
            "name": "xelatex-latexmk-with-shell-escape",
            "command": "latexmk",
            "args": [
                "-f",
                "--shell-escape",
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "-xelatex",
                "-outdir=%OUTDIR%",
                "%DOC%"
            ]
        },
        {
            "name": "pdflatex-latexmk-with-shell-escape",
            "command": "latexmk",
            "args": [
                "-f",
                "--shell-escape",
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "-pdf",
                "-outdir=%OUTDIR%",
                "%DOC%"
            ]
        },
        {
            "name": "latexmk",
            "command": "latexmk",
            "args": [
                "-f",
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "-pdf",
                "%DOC%"
            ]
        },
        {
            "name": "bibtex",
            "command": "bibtex",
            "args": [
                "%DOCFILE%"
            ]
        },
    ],
    // 用于配置编译链
    "latex-workshop.latex.recipes": [
        {
            "name": "xelatex-latexmk",
            "tools": [
                "xelatex-latexmk"
            ]
        },
        {
            "name": "latexmk",
            "tools": [
                "latexmk"
            ]
        },
        {
            "name": "pdflatex-latexmk",
            "tools": [
                "pdflatex-latexmk"
            ]
        },
        {
            "name": "xelatex-latexmk-with-shell-escape",
            "tools": [
                "xelatex-latexmk-with-shell-escape"
            ]
        },
        {
            "name": "pdflatex-latexmk-with-shell-escape",
            "tools": [
                "pdflatex-latexmk-with-shell-escape"
            ]
        },
        {
            "name": "BibTeX",
            "tools": [
                "bibtex"
            ]
        },
    ],
    // 文件清理
    "latex-workshop.latex.clean.fileTypes": [
        "*.log",
        "*.aux",
        "*.bbl",
        "*.blg",
        "*.fdb_latexmk",
        "*.fls",
        "*.out",
        "*.gz",
        "*.lof",
        "*.lot",
        "*.thm",
        "*.toc",
        "*.xdv"
    ],
    "latex-workshop.latex.recipe.default": "lastUsed",
    "latex-workshop.view.pdf.internal.synctex.keybinding": "double-click",
    "latex-workshop.showContextMenu": true,
    "latex-workshop.intellisense.package.enabled": true,
    "[latex]": {
        "editor.formatOnPaste": true,
        "editor.suggestSelection": "recentlyUsedByPrefix"
    },
    "latex-workshop.latex.autoBuild.run": "onSave",
    "explorer.confirmDelete": false,
    "latex-workshop.latex.autoClean.run": "onBuilt",
    "latex-workshop.latex.clean.method": "glob",
    "editor.minimap.enabled": false,
}  
