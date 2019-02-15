## windows系统jenkins+svn+selenium +redmine环境搭建说明
### 1. 环境软件说明
Windows sever

Jenkins

SVN

Python 3.6.3

Selenium 3.141.0

Chrome

Chromedriver

python-redmine 2.1.1

### 2. 服务器安装SVN
略
### 3.Windows服务器环境搭建
#### 3.1   安装Windows sever系统
略
#### 3.2   安装python3.6.3
1.下载安装python，配置环境变量；

2.安装运行环境依赖包；

3.python site-packages路径下新建.pth文件，文件中写入运行python项目路径;
![Alt text](.\images\jenkins_selenium_1.png)

#### 3.3   Jenkins在windows上详细安装（service的msi包安装）与构建部署使用教程
注意：这种安装方式，Jenkins将做为service在windows上安装，GUI测试build时将看不到浏览器。如需要GUI测试build,可新建一个windows slave来build.

Jenkins是一款基于Java开发的持续集成工具，它是一个开源软件项目，旨在提供一个开放易用的软件平台，使软件的持续集成变成可能， 主要可用于持续、自动地构建/测试软件项目，如CruiseControl与DamageControl；监控一些定时执行的任务。

Jenkins为用户提供了一种易于使用的持续集成系统，使开发者从繁杂的集成中解脱出来，专注于更重要的业务逻辑实现上。同时Jenkins能实施监控集成中存在的错误，提供详细的日志文件和提醒功能，还能用图表的形式形象的展示项目构建的趋势和稳定性。
## 

### Jenkins安装介绍
1、要使用Jenkins，首先需要保证系统中已经安装了jdk，如果您的系统还没有安装，可以通过下面的地址下载安装即可。

jdk1.7下载地址：http://www.jb51.net/softs/281781.html

2、加压软件压缩包，点击“jenkins.msi”根据提示完成安装即可, jenkins.msi下载：https://jenkins.io/content/thank-you-downloading-windows-installer/

![Alt text](.\images\jenkins_selenium_2.png)

3、安装后程序会自动创建了一个windows服务，Jenkins默认使用的端口是8080，在浏览器中输入地址：http://localhost:8080/，可打开软件安装界面，如下图所示：

![Alt text](.\images\jenkins_selenium_3.png)

4、找到软件根目录下（默认目录为：C:\Program Files (x86)\Jenkins）secrets文件夹下的initialAdminPassword文件，使用记事本打开，如下图所示：

![Alt text](.\images\jenkins_selenium_4.png)

5、将上面获取的产品密钥复制到Jenkins的安装界面中，点击“continue”继续

![Alt text](.\images\jenkins_selenium_5.png)

6、选择安装插件，左边为所有插件，右边可以自定义安装

![Alt text](.\images\jenkins_selenium_6.png)

7、等待插件下载安装完毕

![Alt text](.\images\jenkins_selenium_7.png)

8、当上面步骤完成之后，第一次运行Jenkins，需要设置管理员信息，如下图所示：

![Alt text](.\images\jenkins_selenium_8.png)

9、输入完毕，点击保存按钮，Jenkins的安装算是全部完毕了，如下图所示：

![Alt text](.\images\jenkins_selenium_9.png)

#### jenkins相关配置参数说明
1、点击左侧“新建”——“Item名称”（JobTest）——“构建一个自由风格的软件项目”——“OK” 

![Alt text](.\images\jenkins_selenium_10.png)

2、暂时不用的相关设置如下：

![Alt text](.\images\jenkins_selenium_11.png)

3、源码管理

![Alt text](.\images\jenkins_selenium_12.png)

![Alt text](.\images\jenkins_selenium_13.png)

4、构建触发器

![Alt text](.\images\jenkins_selenium_14.png)

5、构建——增加构建步骤

![Alt text](.\images\jenkins_selenium_15.png)

![Alt text](.\images\jenkins_selenium_16.png)


6、构建后操作——增加构建后操作步骤

![Alt text](.\images\jenkins_selenium_17.png)

7、点击保存，跳转到下图，一个基本job项目建立

![Alt text](.\images\jenkins_selenium_18.png)

8、构建项目——左侧“立即构建”

![Alt text](.\images\jenkins_selenium_19.png)

9、构建之后查看构建结果，点击构建历史，点击选择——ConsoleOutput控制台输出，如下图所示，到此简单的jenkins构建流程完成

![Alt text](.\images\jenkins_selenium_20.png)

~~~
How to install Jenkins (jenkins-2.32.3.zip)
  1.Download Jenkins from 
    https://jenkins.io/content/thank-you-downloading-windows-installer/#stable
  2.Unzip jenkins-2.32.3.zip
  3.Install by double clicking jenkins.msi
Jenkins URL
  http://localhost:8080
Jenkins login
  admin/admin
Jenkins : How to make Selenium GUI tests visible on Windows
  Please refer to http://stackoverflow.com/questions/13639358/integration-of-selenium-webdriver-with-hudson-unable-to-open-the-browser
~~~
