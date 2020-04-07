#####  中英文混排

直接使用XeLaTex编译即可，不要用pdfLaTex，也无需使用ctex包。

##### 添加引用

1. 在.tex文件的同一文件夹下创建.bib文件，比如ref.bib，将需要引用的文献的bibtex信息复制到其中。

2. 在主文件.tex中，\begin{document}之前加入

   ```latex
   \usepackage{cite}
   ```

   在正文中，需要引用文献时，加入

   ```latex
   \cite{文献的标识符}
   ```

   在正文的最后，\end{document}之前加入

   ```latex
   \bibliographystyle{plain}
   \bibliography{ref}
   ```

   其中的plain是引用的显示模式，可以更换；ref是.bib文件的名称，根据实际文件名填写即可。

3. * 正常编译.tex文件
   * 成功编译.tex文件后，会在.tex文件的同一文件夹下生成与.tex文件同名的.aux文件，使用BibTex编译.aux文件
   * 再次正常编译.tex，此时被引用的文献信息应该已经出现在了文末的文献列表中，但是正文中的编号应该还有问题
   * 再次正常编译.tex，此时正文中引用的编号应该也正确了。

4. 更改了.tex文件中的引用信息后，需要重复步骤3.

##### 调整页边距等

```latex
\usepackage{geometry}
\geometry{papersize={20cm,15cm}}
\geometry{left=2.0cm,right=2.0cm,top=2.0cm,bottom=2.0cm}
```

##### 插入图片

后两行在正文中出现

```latex
\usepackage{graphicx}
\includegraphics{a.jpg}
\includegraphics[width = .8\textwidth]{a.jpg}
```

