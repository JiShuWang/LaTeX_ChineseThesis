# LaTeX_ChineseThesis
一个用于国内研究生学位论文撰写的LaTeX模板及其基本使用教程。该模板最初是用于云南大学研究生学位论文的撰写，但国内的学位论文格式基本一致，因此也可根据自己的需求扩展到各个高校的研究生学位论文撰写。如有任何问题和建议，欢迎Issue。

使用LaTeX编写学位论文，不仅可以符合长期使用LaTeX编写学术论文的研究者的习惯，也可以同时避免使用Word撰写论文过程中经常面临的图表位置错乱、模板不一致、参考文献格式不统一等问题，从而提高论文撰写效率，并实现标准的论文格式。
## 1.论文编写环境配置
在线工具：推荐Overleaf，支持在线、多人协作等功能，同时不用配置环境，但最近由于编译时长的缩短，大篇幅的学位论文很难通过编译。
本地部署（也是本教程中所采用的方案）：首先安装TeX Live，然后使用VSCode作为编写工具，并在VSCode中安装LaTeX和LaTeX Workshop这两个插件。后续的论文撰写将严格依赖于插件的配置。具体流程请参阅：https://github.com/James-Yu/LaTeX-Workshop/wiki/Install。

## 2.目录结构
Figures：存放论文中需要插入的各类图片。

fonts：存放中文学位论文中使用的主要字体。

main.bib：存放论文中需要引用的参考文献。

main.tex：主文档，即论文撰写的主要文件。

main.pdf：编译后的论文。

其它文件均为配置文件，请勿随意改动或删除。

## 3.注意事项
由于默认的LaTeX环境使用latex编译器，而该编译器不支持中文论文的编译，所以需要修改默认（首选）的编译器。同时由于LaTeX编译后会自动生成一些文件，还需要自动完成对这些文件的清理。此外，还有一些其它的配置项（如是否用浏览器打开编译后的pdf文件）需要根据需求自行配置，所以提供一个可用的配置模板（Template.json），直接将该模板复制，然后找到LaTeX Workshop中的settings.json文件（或者在settings中查找recipes并编辑该文件），将该模板粘贴即可。

## 4.参考来源
[1] https://zhuanlan.zhihu.com/p/581508127

[2] https://blog.csdn.net/qq_41554005/article/details/120698428

[3] https://blog.csdn.net/CYW2014_HUST/article/details/121676646

## 5.致谢
感谢该模板原始版本的提供者Rui-Zhi Li（liruizhi0871@gmail.com）
。在此基础上，Xue Wang（wangxue2022@mail.ynu.edu.cn；https://github.com/wang-x-1997）
完成了第一版模板的编写。

在此基础上，我进一步修改了模板，并将环境配置和可能遇到的主要问题进行排查解决，并编写了该教程。

衷心地感谢他们。
