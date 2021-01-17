---
title: 基于Hexo+GitHub_Gitee搭建个人博客
tag: 
	- Hexo
	- GitHub
	- Gitee
	- Blog
categories: 
	- PersonalBlog 
---

>自由和山巅上的空气相似，对弱者都是吃不消的。
    <p align="right">——芥川龙之介 《侏儒的话》。</p>

<hr>

# 预备工作
## 1、安装 Node.js
 [官网下载链接地址：](https://nodejs.org)https://nodejs.org

<font face="楷体" >选择当前的LTS版本</font>
![选择当前的LTS版本](https://img-blog.csdnimg.cn/20210111162259365.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3UwMTMwMTIzNjk=,size_16,color_FFFFFF,t_70#pic_center)
<font face="楷体" >安装步骤非常简单，一直next，下一步就可以了，默认安装就行。</font>

```bash
node -v		//查看node.js版本，验证是否安装成功
```
![node.js版本](https://img-blog.csdnimg.cn/2021011116350191.png#pic_center)
<hr>

## 2、安装 Git
<font face="楷体" > [官网下载链接地址：](https://git-scm.com/downloads)https://git-scm.com/downloads</font>
![下载Windows最新版git](https://img-blog.csdnimg.cn/20210111170302943.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3UwMTMwMTIzNjk=,size_16,color_FFFFFF,t_70#pic_center)
<font face="楷体" >选择当前的最新版本</font>
>具体win10下git安装过程参考：https://blog.csdn.net/Deng872347348/article/details/111883306

```bash
git --version			//查看当前git版本，验证git是否安装成功
```
![git版本查看](https://img-blog.csdnimg.cn/20210111171820594.png#pic_center)
>**Tips**：这个Git Bash下载下来就相当于Linux中的终端窗口了，以后我们就用这个来打开终端。

<hr>

# 安装 Hexo
## 创建blog本地目录
<font face="楷体" >新建一个文件夹，比如我这里建了 ==Hexoblog==
打开你的文件夹，然后在空白处点鼠标的右键，选择 ==Git Bash Here==</font>

<font face="楷体" >看看 ==node，npm== 是否安装成功，没有成功的就重新安装node。</font>
![node & npm](https://img-blog.csdnimg.cn/20210111190015814.png#pic_center)
<hr>

## Node.js换源

<font face="楷体" >Node.js 官方源：==http://registry.npmjs.org==，为避免网络问题，可将其替换为淘宝源：==http://npm.taobao.org==。</font>
```bash
npm install -g cnpm --registry=https://registry.npm.taobao.org
```

<font face="楷体" >换源后测试cnpm，如果能输出相关介绍，则说明成功了：<code>cnpm </font>

![cnpm](https://img-blog.csdnimg.cn/20210111191904445.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3UwMTMwMTIzNjk=,size_16,color_FFFFFF,t_70#pic_center)
<hr>

## 安装hexo

```bash
cnpm install -g hexo-cli		// 通过npm全局安装hexo
```
<font face="楷体" >其中，-g 指定全局安装，之后可以在任意位置使用 hexo 命令</font>

- <font face="楷体" >验证是否安装成功：<code>hexo -v </font>


![hexo](https://img-blog.csdnimg.cn/20210111192257365.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3UwMTMwMTIzNjk=,size_16,color_FFFFFF,t_70#pic_center)

 - <font face="楷体" >首先看看当前路径：<code>pwd </font> 

- <font face="楷体" >然后我们运行命令<code>hexo init </font>  <font face="楷体" >。这步是关键，主要是建立整个项目，这里我博客所在的文件夹（事先创建）名字是Hexoblog，文件夹位置是d盘根目录上。文件目录及其分析如下：</font> 
![hexo init](https://img-blog.csdnimg.cn/20210111193753849.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3UwMTMwMTIzNjk=,size_16,color_FFFFFF,t_70#pic_center)
![项目目录文件生成](https://img-blog.csdnimg.cn/20210111193832725.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3UwMTMwMTIzNjk=,size_16,color_FFFFFF,t_70#pic_center)
![hexo blog目录](https://img-blog.csdnimg.cn/20210111194639505.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3UwMTMwMTIzNjk=,size_16,color_FFFFFF,t_70#pic_center)

 <font face="楷体" >其中，目录Hexoblog\source\_posts下存放都为makedown（md）格式文件，也就是写好的blog文件。</font>

<font color="red">
Notes：也可以在git bash中完成目录创建，步骤如下</font>

```bash
hexo init Hexoblog      # 初始化创建，会在你所在位置创建 blog 文件夹
cd Hexoblog             # 进入 blog 目录
npm install         	# 进一步安装hexo所需文件
```

<hr>

## 运行测试

 <font face="楷体" >这里我们经常用到的有3个命令（第三个仅用于本地测试）</font> 

```bash
hexo clean 		#用来清理缓存文件
hexo g          #生成文件
hexo  s     	#运行本地服务器
hexo  d   		#上传到服务器
```
<font face="楷体" >运行</font> <code>hexo s

![hexo -s](https://img-blog.csdnimg.cn/20210111195441749.png#pic_center)

<font face="楷体" >接下来输入</font>

```bash
hexo clean                # 清除所有记录
hexo generate       	  # 生成静态网页
hexo server (-p 80可选)   # 启动服务, -p 80 表示端口号为 80，默认不加端口号是 4000
```

<font face="楷体">然后，使用浏览器访问：http://localhost:80，就可以看到下面的界面了。</font>
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210111195514688.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3UwMTMwMTIzNjk=,size_16,color_FFFFFF,t_70#pic_center)
<font face="楷体" >至此说明本地环境搭建完成。</font> 

<hr>

## 主题替换
> 默认主题也不是说不好看，就是怕烂大街，谁不想在自己的地盘彰显点个性化呢...

<font face="楷体" >官方提供的[参考主题](https://hexo.io/themes/)：https://hexo.io/themes/， 这里以[Sakura主题](https://github.com/honjun/hexo-theme-sakura)：https://github.com/honjun/hexo-theme-sakura为例</font> 

- <font face="楷体" >进入github点击下载zip：https://github.com/honjun/hexo-theme-sakura</font>
- <font face="楷体" >将压缩包解压，并将其中theme文件夹拷贝至目录<code>Hexoblog/themes</font>
![sakura.zip](https://img-blog.csdnimg.cn/2021011120263117.jpg#pic_center)
![unzip](https://img-blog.csdnimg.cn/20210111202701105.jpg#pic_center)
![themes文件夹](https://img-blog.csdnimg.cn/20210111202725353.jpg#pic_center)
- <font face="楷体" >修改配置文件：主题配置在Hexoblog主目录找到：_config.yml，记事本打开并修改默认theme: landscape为<code>theme:sakura</font>

![_config.yml](https://img-blog.csdnimg.cn/20210111203315140.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3UwMTMwMTIzNjk=,size_16,color_FFFFFF,t_70#pic_center)
![Sakura](https://img-blog.csdnimg.cn/20210111203332435.jpg#pic_center)
 <font face="楷体" >接着，本地测试主题是否替换成功<font/>
 
```bash
hexo clean
hexo g		//hexo generate
hexo s		//hexo server
```
<hr>

# Gitee配置
>Gitee配置很简单，简要记录几点。
>详细参考：https://blog.csdn.net/cungudafa/article/details/104260494

- 新建的仓库名称必须和gitee用户名一致。
- 每次都需要记得手动更新Gitee端

## 效果图：
![giteeblog](https://img-blog.csdnimg.cn/20210111215112437.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3UwMTMwMTIzNjk=,size_16,color_FFFFFF,t_70#pic_center)

> 蛮酷的有没有...
<hr>

# Github配置
>Github配置大同小异，简要记录几点注意事项。
>详细参考：https://www.jianshu.com/p/f9b213097c42

- 出现<font color="red"  face="楷体">nothing to commit, working tree clean，且网页404。</font>
![404](https://img-blog.csdnimg.cn/20210111212745820.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3UwMTMwMTIzNjk=,size_16,color_FFFFFF,t_70#pic_center)
  则hexo的提交命令使用：<code>hexo clean && hexo g && hexo d

- GitHub新建仓库时，仓库名必须为用户名<code>.github.io
- 同时部署GitHub和Gitee的时候，_config_yml中deploy部分如下所示：

```bash
deploy:
  type: git
  repo: 
        github: git@github.com:用户名/用户名.github.io.git
        gitee: https://gitee.com/用户名/用户名  //因为开启了强制HTTPS
  branch: master
```
- GitHub中新建的仓库code中必须要有README.md文件，不然还是会出现404。
- 内容只有放在在master分支里面的内容才能用github.io查看到

## 效果图
![githubpage](https://img-blog.csdnimg.cn/20210111215219759.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3UwMTMwMTIzNjk=,size_16,color_FFFFFF,t_70#pic_center)
<hr>
接下来就是自由发挥的空间了，未完待续。。。
