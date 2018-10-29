# \[第一章\]

**1.shell脚本不执行**

问题：某天研发某同事找我说帮他看看他写的shell脚本，死活不执行，报错。我看了下，脚本很简单，也没有常规性的错误，报“:badinterpreter:Nosuchfileordirectory”错。

看这错，我就问他是不是在windows下编写的脚本，然后在上传到linux服务器的……果然。

原因：在DOS/windows里，文本文件的换行符为rn，而在\*nix系统里则为n，所以DOS/Windows里编辑过的文本文件到了\*nix里，每一行都多了个^M。

解决：

1）重新在linux下编写脚本；

2）vi:%s/r//g:%s/^M//g（^M输入用Ctrl+v,Ctrl+m）

附：sh-x脚本文件名，可以单步执行并回显结果，有助于排查复杂脚本问题。  


