Ubuntu 环境下 python等环境配置方法
 
## 目录
* [概要](#chapter1)
* [顺序](#chapter2)
* [详细](#chapter3)

<a id="chapter1"></a>

### 概要
    - Windows环境下 构建ubuntu OS的 AI环境配置安装内容一览

<a id="chapter2"></a>

### 顺序
    1. Windows环境下安装VirtualBox 最新版。
    2. 下载ubuntu20.04 ios镜像。
    3. 在虚拟机上安装 ubuntu 系统。
    4. 进入ubuntu 终端程序内进行系统更新和开源软件的安装
    5. 开启jupyter编译环境
    6. 测试环境

<a id="chapter3"></a>

### 详细说明
   1.Windows 环境下 安装VirtualBox 最新版
   [安装VirtualBox链接](https://www.oracle.com/jp/virtualization/technologies/vm/downloads/virtualbox-downloads.html)
   
   2.下载 ubuntu20.04 ios 镜像文件 Desktop image
   [下载ubuntu20.04链接](https://releases.ubuntu.com/focal/)
   
   3.按照配置指南 安装ubuntu os  （内存4GB以上，最好选择English 语言， 中文今后命令操作会很麻烦。 密码简单一点比较好， 最好不使用特殊字符）
   [参考blog](https://blog.csdn.net/a805607966/article/details/105877055)


  #### comment:上述环境大概20分钟能搞定
  
  
   4.进入ubuntu系统在程序里 找到 终端（terminal）打开，
      ##### 执行如下命令
         sudo apt update
         sudo apt upgrade

      ##### 然后安装 pyenv， python3 ，pip3，git，pandas，scikit-learn，matplotlib，jupyter， 等命令群
        ###### git安装如下
           sudo apt install git

        ###### pip3 安装如下
           sudo apt install python3-pip

        ###### pyenv 安装方法看 手册 
           [参考pyenv安装手册]（https://github.com/pyenv/pyenv/wiki）

        ###### 然后在pyenv环境下安装python3
           比如执行如下命令
             pyenv install --list
           然后选你想安装的版本
             pyenv install 3.9.1
             pyenv global 3.9.1
             pyenv rehash

        ###### pandas，scikit-learn，matplotlib的话
           pip3 install pandas,scikit-learn,matplotlib

        ###### jupyter 安装看官网指南
           [参考jupyter官方安装说明]（https://jupyter.org/）


   5.在终端程序内启动 jupyter notebook 或者 lab 
        jupyter notebook
      
   6.打开之后建立新的文本 测试如下代码

           import matplotlib.pyplot as plt

           fig, ax = plt.subplots()

           fruits = ['apple', 'blueberry', 'cherry', 'orange']
           counts = [40, 100, 30, 55]
           bar_labels = ['red', 'blue', '_red', 'orange']
           bar_colors = ['tab:red', 'tab:blue', 'tab:red', 'tab:orange']

           ax.bar(fruits, counts, label=bar_labels, color=bar_colors)

           ax.set_ylabel('fruit supply')
           ax.set_title('Fruit supply by kind and color')
           ax.legend(title='Fruit color')

           plt.show()
           
           
           
       效果图如下
         [Image and Code](https://matplotlib.org/stable/gallery/lines_bars_and_markers/bar_colors.html#sphx-glr-gallery-lines-bars-and-markers-bar-colors-py)

  #### comment:上述安装大概10分钟能搞定

