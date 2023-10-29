# Copyrights are not reserved, so you can use freely.
# Here is to give you the solution about how to install python from its source code and tensorflow framework from its release package
# Author : Gx Zhong
# Date   : 2023.10.29 Morning

1、安装python 3.9
1) 下载python源代码:
在python.org下载 python的源代码，解压到你指定的目录 dstDir。这个后续作为python的interpreter目录。官网的下载速度比较慢，可以改为在国内的镜像源下载，入清华、阿里、中科大等的源。
如要使用tensorflow框架，建议选择https://www.python.org/downloads/python3.9

2) 版本管理工具git：
http://git-scm.com/download/win，下载git工具，
然后在dstDir建立repo，
~> git init
~> git add <filename>
~> git commit

3) VC++编译环境：
(1)下载、安装 vcredist；
https://aka.ms/vs/17/release/vc_redist.x64.exe

(2)下载、安装 visual studio 2022版本。
https://visualstudio.microsoft.com/zh-hans/downloads/

4) 在 dstDir\pcbuild\get_externals.bat
dstDir\pcbuild\build.bat -e -p x64
此处如果出错，一般是python的源代码要求基于visual studio 2019版本。解决方法：用vs2022打开 pcbuild.sln，在vs的 项目 菜单栏，选择 重定目标解决方案，升级为采用vc++编译器版本为vs2022，重新构建。

5)python安装后，缺少了pip包管理工具。
~>python -m ensurepip --default-pip
这将会使用Python自带的ensurepip模块来安装pip。如果成功，Python的安装目录下会多出一个Scripts文件夹，里面会有一个pip.exe文件。
建议把pip所在路径添加到用户path环境。


2、安装tensorflow。
建议使用清华的安装镜像源
pip install tensorflow -i https://pypi.tuna.tsinghua.edu.cn/simple
