# README

这是我记的量子力学课程笔记，每节课后都会更新，欢迎大家参考和fork。

我使用的Markdown格式，并且用了一点Pandoc markdown的方言。大家可以直接用文本编辑器看源文件（Markdown就算没用过也应该能明白意思），也可以看生成的html文件。

生成HTML需要安装[pandoc](http://pandoc.org/)，Windows，Mac，Linux都支持。然后在命令行执行：

```
pandoc -f markdown+latex_macros -t html -s --number-sections --mathjax notes.md -o notes.html
```
就可以了。

