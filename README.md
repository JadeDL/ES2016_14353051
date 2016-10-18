# DOL配置实验报告
学号：145353051       姓名：邓玲
##安装必要环境
$ sudo apt-get update
$ sudo apt-get install ant
$ sudo apt-get install openjdk-7-jdk
$ sudo apt-get install unzip
##在安装这些环境时都进行的很流畅。
下载文件
$ sudo wget http://www.accellera.org/images/downloads/standards/systemc/systemc-2.3.1.tgz
$ sudo wget http://www.tik.ee.ethz.ch/~shapes/downloads/dol_ethz.zip
## 解压文件
1. 新建dol的文件夹
$ mkdir dol

2. 将dolethz.zip解压到 dol文件夹中
$ unzip dol_ethz.zip -d dol
3. 解压systemc
$ tar -zxvf systemc-2.3.1.tgz
## 编译systemc
1. 解压后进入systemc-2.3.1的目录下
$ cd systemc-2.3.1
2. 新建一个临时文件夹objdir
$ mkdir objdir

3. 进入该文件夹objdir
$ cd objdir

4. 运行configure（能根据系统的环境设置一下参数，用于编译）
$ ../configure CXX=g++ --disable-async-updates
下图为运行configure之后的截图 

  
5. 编译
$ sudo make install
编译完后文件目录如下($cd .. $ls) 
  
6. 记录当前的工作路径（会输出当前所在路径，记下来，待会有用）
$ pwd
## 编译dol
1. 进入刚刚的dol文件夹，修改build.xml文件 
找到下面这段话，就是说上面编译的systemc位置在哪里
property name=”systemc.inc” value=”YYY/include” 
property name=”systemc.lib” value=”YYY/lib-linux/libsystemc.a”/
把YYY改成上页pwd的结果（注意，对于 64位 系统的机器，lib-linux要改成lib-linux64） 

2. 编译
$ ant -f build_zip.xml all
若成功会显示build sucessful 

3. 运行第一个例子

进入build/bin/main路径下
$ cd build/bin/main
然后运行第一个例子
$ ant -f runexample.xml -Dnumber=1
主要在这一步遇到了问题，由于这里一直没有成功，后来重装了很多次，记过在课上TA帮忙装饰才发现自己在前面修改linux时以为自己的是linux64，结果一直没有成功，后来改了以后再装就运行成功了，在这里成功结果如图所示
   
## 在版本控制中遇到的问题：
1. 仓库地址写错，后来initial以后还是不能连接，最后只能删除新建的整个git文档，然后重新开始做，再远程连接，然后才可；


如下图所示，更改为正确仓库地址以后可以成功push

在commit的时候遇到该问题，是因为提前没有输入git add .语句

先把文件add，然后得到commit结果如成功，如图所示：

之后就在markdown下编写自己的DOL实验心得：
在DOL配置过程中主要是由于粗新，输错一些语句，导致最后一步一直没有成功，后来只能重新配置，发现自己之前出现的问题都是由于自己过于粗心，后来在TA的知道下终于配置成功。
