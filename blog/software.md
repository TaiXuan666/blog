# node安装

## nvm的安装

nvm（Node Version Manager）： 用来管理node版本

官方地址：https://nvm.uihtm.com/doc/download-nvm.html

进入官网地址安装最新的版本即可:

![](java软件开发工具.assets/image-20250911130502685.png)

打开文件夹所在位置解压到选择的文件夹



![image-20250911130739283](java软件开发工具.assets/image-20250911130739283.png)



![image-20250911130828725](java软件开发工具.assets/image-20250911130828725.png)



新建一个文件夹把文件解压到文件目录 注意：文件名尽量不要有空格、中文 , 也不要太深

![image-20250911131039139](java软件开发工具.assets/image-20250911131039139.png)



双击exe文件安装

![image-20250911131105935](java软件开发工具.assets/image-20250911131105935.png)

![image-20250911131155114](java软件开发工具.assets/image-20250911131155114.png)

![image-20250911131212310](java软件开发工具.assets/image-20250911131212310.png)

![image-20250911131621128](java软件开发工具.assets/image-20250911131621128.png)



​							接下来一直next下一步即可

![image-20250911131645844](java软件开发工具.assets/image-20250911131645844.png)

![image-20250911131656213](java软件开发工具.assets/image-20250911131656213.png)

![image-20250911131718824](java软件开发工具.assets/image-20250911131718824.png)





添加环境变量



1.复制带有exe文件的目录添加到系统环境变量

![image-20250911132012423](java软件开发工具.assets/image-20250911132012423.png)

![image-20250911132038784](java软件开发工具.assets/image-20250911132038784.png)

![image-20250911132052820](java软件开发工具.assets/image-20250911132052820.png)

![image-20250911132125493](java软件开发工具.assets/image-20250911132125493.png)

验证一下

![](java软件开发工具.assets/image-20250911132226956.png)



## 使用nvm安装node

先看一下可用的安装版本 选择自己合适的就好了，这里安装的是最新版本

![image-20250911132619731](java软件开发工具.assets/image-20250911132619731.png)

安装完成之后node也配置一下环境变量

![image-20250911133012951](java软件开发工具.assets/image-20250911133012951.png)

![image-20250911133049147](java软件开发工具.assets/image-20250911133049147.png)

验证一下node是否配置成功

![image-20250911133132341](java软件开发工具.assets/image-20250911133132341.png)





# jdk安装

如果想自定义存放安装目录的话 , 可以新建一个空的java文件夹存放jdk  。也可以安装系统默认的安装环境即可，直接一直下一步即可

双击jdk-8u172-windows-x64.exe文件，接下来安装操作步骤即可

![image-20250911144901817](java软件开发工具.assets/image-20250911144901817.png)

接下来等待一下, 可以选择安装到默认路径,也可以选择安装到自己的目录，这里是在java文件夹下又新建了一个空的java文件夹

![image-20250911145254218](java软件开发工具.assets/image-20250911145254218.png)

等待安装完即可

![image-20250911145402368](java软件开发工具.assets/image-20250911145402368.png)



接下来配置一下环境变量

![image-20250911145755316](java软件开发工具.assets/image-20250911145755316.png)

![image-20250911145811340](java软件开发工具.assets/image-20250911145811340.png)

![image-20250911145825791](java软件开发工具.assets/image-20250911145825791.png)

![image-20250911150408931](java软件开发工具.assets/image-20250911150408931.png)

配置完在终端验证一下

![image-20250911150453127](java软件开发工具.assets/image-20250911150453127.png)





# maven安装

1.解压文件到你自定义的文件夹里

![image-2025110911244](java软件开发工具.assets/image-2025110911244.png)

2.解压完，检查解压的文件，进入apache-maven-3.6.3文件夹

![image-20250911152315430](java软件开发工具.assets/image-20250911152315430.png)

到这一步就完成了，下一步就是配置环境变量

3.配置环境变量：

1. 按【Win + R】调起“运行”窗口，输入：sysdm.cpl，打开系统属性窗口：

   ![微信图片_20250911152639](java软件开发工具.assets/微信图片_20250911152639.jpg)

   2. 然后选择“高级”-“环境变量”，打开环境变量设置窗口：

      

![微信图片_20250911152643](java软件开发工具.assets/微信图片_20250911152643.jpg)

![微信图片_20250911152648](java软件开发工具.assets/微信图片_20250911152648.jpg)

3. 环境变量有当前用户的，以及系统级别的，我们一般使用系统变量，采用系统级别的配置

4. 新建“MAVEN_HOME”环境变量，定位路径到“C:\\Program Files\\apache-maven-3.6.3”：

   ![微信图片_20250911153128](java软件开发工具.assets/微信图片_20250911153128.jpg)

   ![微信图片_20250911153135](java软件开发工具.assets/微信图片_20250911153135.jpg)

5. 确定保存后，再次查看列表，已经出现了刚刚添加的变量：

   ![微信图片_20250911153141](java软件开发工具.assets/微信图片_20250911153141.jpg)

6. 再次把“MAVEN_HOME”的变量配置到“Path”变量上，使其生效，定位到“Path”变量，选择“编辑”：

   ![微信图片_20250911153146](java软件开发工具.assets/微信图片_20250911153146.jpg)

7. 然后在对话框下面新建变量，把“MAVEN_HOME”加上：%MAVEN_HOME%\\bin

   1. 扩展：在 Windows 下环境变量获取一般是双百分号，比如 Path 的变量获取：%Path%

      ![微信图片_20250911153150](java软件开发工具.assets/微信图片_20250911153150.jpg)

      ![微信图片_20250911153155](java软件开发工具.assets/微信图片_20250911153155.jpg)

8. 最后别忘记选择“确定”保存。

9. 验证， 按【Win + R】调起“运行”窗口，输入：cmd，打开命令行：

   ![微信图片_20250911153915](java软件开发工具.assets/微信图片_20250911153915.jpg)

10. 输入命令：mvn -version

    ![微信图片_20250911153917](java软件开发工具.assets/微信图片_20250911153917.jpg)

11. 再输入命令：echo %MAVEN_HOME%

    ![微信图片_20250911153922](java软件开发工具.assets/微信图片_20250911153922.jpg)

12. 再输入命令：echo %Path%

    ![微信图片_20250911153926](java软件开发工具.assets/微信图片_20250911153926.jpg)

13. 出现如上信息表示环境安装正确





# IDEA安装

一。

1.安装步骤

进入"idea"文件夹，双击打开"ideaIU-2023.3.2.exe"

![20250911143441.png](java软件开发工具.assets/20250911143441.png)

2.选择下一步

![20250911132112](java软件开发工具.assets/20250911132112.png)

3.默认安装在C盘，这里我安装在D盘，选择下一步

![20250911132345](java软件开发工具.assets/20250911132345.png)

4.把配置项都勾选上，选择下一步

![20250911132522](java软件开发工具.assets/20250911132522.png)

5.选择安装

![微信图片_20250911143856](java软件开发工具.assets/微信图片_20250911143856.jpg)

6.安装过程可能比较慢，耐心等待片刻，安装完成后，选择否，不重启，然后点击完成

![20250911132617](java软件开发工具.assets/20250911132617.png)

7.此时桌面上会有这个图标

![20250911132817](java软件开发工具.assets/20250911132817.png)

二。

1.注册， 进入文件夹：“\\JetBrains  2024 最新全家桶激活\\方式3：永久激活补丁+脚本（适合最新版本，可显示到2025年）”：

![20250911133328](java软件开发工具.assets/20250911133328.png)

2.复制"jetbra"整个文件夹到你安装的idea文件夹，粘贴到目标目录的过程会出现安全提示，选择"继续"

![20250911133350](java软件开发工具.assets/20250911133350.png)

3.最后得到的路径为：D:\idea

4.按【Win + R】快捷键，调起“运行”窗口，输入“cmd”，然后按【Shift + Ctrl + Enter】组合键，以管理员身份运行命令行窗口：

![20250911140011](java软件开发工具.assets/20250911140011.png)

通过管理员身份运行的命令行窗口，会有提权确认，选择“是”，此时打开的命令行窗口左上角会有“管理员”字样，这个是确认是否已经正确以管理员身份运行的重要提示，如果没有，则说明没有提权成功。

![20250911140132](java软件开发工具.assets/20250911140132.png)

5.在命令行窗口，先输入d:，然后cd进入"D:\idea\jetbra\scripts"，然后执行“install-all-users.vbs”：

6.运行完会有确认配置提示，选择“确定”，这一步的目的是写入环境变量：

![20250911 140656](java软件开发工具.assets/20250911 140656.png)

7.接着是漫长的等待，等个 1-5 分钟，最后成功会有“Done”的提示，如果没有说明注册不成功

![微信图片_20250911144334](java软件开发工具.assets/微信图片_20250911144334.jpg)

8.桌面打开运行：IntelliJ IDEA，首次启动会弹出注册界面，此时选择“Activation Code”选项：

![微信图片_20250911144505](java软件开发工具.assets/微信图片_20250911144505.jpg)

![微信图片_20250911144510](java软件开发工具.assets/微信图片_20250911144510.jpg)

![微信图片_20250911144516](java软件开发工具.assets/微信图片_20250911144516.jpg)

![微信图片_20250911144521](java软件开发工具.assets/微信图片_20250911144521.jpg)

9.输入下面序列号，复制来粘贴可以避免格式问题：

```
6G5NXCPJZB-eyJsaWNlbnNlSWQiOiI2RzVOWENQSlpCIiwibGljZW5zZWVOYW1lIjoic2lnbnVwIHNjb290ZXIiLCJhc3NpZ25lZU5hbWUiOiIiLCJhc3NpZ25lZUVtYWlsIjoiIiwibGljZW5zZVJlc3RyaWN0aW9uIjoiIiwiY2hlY2tDb25jdXJyZW50VXNlIjpmYWxzZSwicHJvZHVjdHMiOlt7ImNvZGUiOiJQU0kiLCJmYWxsYmFja0RhdGUiOiIyMDI1LTA4LTAxIiwicGFpZFVwVG8iOiIyMDI1LTA4LTAxIiwiZXh0ZW5kZWQiOnRydWV9LHsiY29kZSI6IlBEQiIsImZhbGxiYWNrRGF0ZSI6IjIwMjUtMDgtMDEiLCJwYWlkVXBUbyI6IjIwMjUtMDgtMDEiLCJleHRlbmRlZCI6dHJ1ZX0seyJjb2RlIjoiSUkiLCJmYWxsYmFja0RhdGUiOiIyMDI1LTA4LTAxIiwicGFpZFVwVG8iOiIyMDI1LTA4LTAxIiwiZXh0ZW5kZWQiOmZhbHNlfSx7ImNvZGUiOiJQUEMiLCJmYWxsYmFja0RhdGUiOiIyMDI1LTA4LTAxIiwicGFpZFVwVG8iOiIyMDI1LTA4LTAxIiwiZXh0ZW5kZWQiOnRydWV9LHsiY29kZSI6IlBHTyIsImZhbGxiYWNrRGF0ZSI6IjIwMjUtMDgtMDEiLCJwYWlkVXBUbyI6IjIwMjUtMDgtMDEiLCJleHRlbmRlZCI6dHJ1ZX0seyJjb2RlIjoiUFNXIiwiZmFsbGJhY2tEYXRlIjoiMjAyNS0wOC0wMSIsInBhaWRVcFRvIjoiMjAyNS0wOC0wMSIsImV4dGVuZGVkIjp0cnVlfSx7ImNvZGUiOiJQV1MiLCJmYWxsYmFja0RhdGUiOiIyMDI1LTA4LTAxIiwicGFpZFVwVG8iOiIyMDI1LTA4LTAxIiwiZXh0ZW5kZWQiOnRydWV9LHsiY29kZSI6IlBQUyIsImZhbGxiYWNrRGF0ZSI6IjIwMjUtMDgtMDEiLCJwYWlkVXBUbyI6IjIwMjUtMDgtMDEiLCJleHRlbmRlZCI6dHJ1ZX0seyJjb2RlIjoiUFJCIiwiZmFsbGJhY2tEYXRlIjoiMjAyNS0wOC0wMSIsInBhaWRVcFRvIjoiMjAyNS0wOC0wMSIsImV4dGVuZGVkIjp0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
```

10.接着点击：“Activate”：

![微信图片_20250911144733](java软件开发工具.assets/微信图片_20250911144733.jpg)

如果这一步不成功，可能是上面的注册脚本运行错误或者没有成功，此时关闭所有的 IDEA 进程，然后再次运行上面的注册脚本，直到出现“Done”为止，出现之后再次启动 IDEA 进行注册，如果出现了 Done 还是不行，那么进行重启系统，再打开 IDEA 试一次。

11.成功，选择"Continue"退出：

![微信图片_20250911144737](java软件开发工具.assets/微信图片_20250911144737.jpg)

12.选择不发送：

![微信图片_20250911144741](java软件开发工具.assets/微信图片_20250911144741.jpg)

13.到这一步就全部配置完成了

14.序列号显示到期为2025，如果到期了，可以通过下面网址进行获取最新的激活序列号，重新激活即可。

序列号更新地址：http://jets.idejihuo.com

三。

1.配置JDK，  刚开始打开 IDEA 时，如果没有任何项目，那么此时看到的是如下页面：

![微信图片_20250911144929](java软件开发工具.assets/微信图片_20250911144929.jpg)

 一般这个界面对于配置不太友好，所以，我们先新建一个 Java 工程，然后打开工程，进入到那个页面来配置会方便很多。

2.新建Java工程步骤如下：

在主界面选择"New Project"：

![微信图片_20250911144936](java软件开发工具.assets/微信图片_20250911144936.jpg)

或者已经打开了原来的项目时，可以这样创建工程："File"-"New"-"Project"：

此时打开如下界面，并填写相应信息：

![微信图片_20250911144941](java软件开发工具.assets/微信图片_20250911144941.jpg)

3.上面的配置选择保存的路径为：c:\\projects；编译采用的是 Maven；JDK 使用的是 IDEA 默认识别的 JDK，这里先不用管它，直接用默认的。高级配置填写了包名和应用名，这个是默认的，也不用管它；

4.点击"Create"按钮继续

![微信图片_20250911144946](java软件开发工具.assets/微信图片_20250911144946.jpg)

5.此时 Maven 开始下载所需要的包，右下角的进度条就是下载包的进度，一般来说只要网络正常，等待片刻就会全部完成的，完成下载页面如下：

![微信图片_20250911145229](java软件开发工具.assets/微信图片_20250911145229.jpg)

6.接着我们整理一下页面，把一些窗口先隐藏起来，圈起来部分点击一下就行了：

![微信图片_20250911145234](java软件开发工具.assets/微信图片_20250911145234.jpg)

7.完成好后的页面如下：

![微信图片_20250911145244](java软件开发工具.assets/微信图片_20250911145244.jpg)

8.接着点击“Main”方法，然后再点一下右边的小三角形，此时会出现一个菜单，菜单里面选择第一项，这个是开始运行的步骤，先跑一下测试一下：

![微信图片_20250911145249](java软件开发工具.assets/微信图片_20250911145249.jpg)

9.运行结果如下

![微信图片_20250911145254](java软件开发工具.assets/微信图片_20250911145254.jpg)

 可以看到底部的控制台已经升起来，并且输出我们代码的打印信息了，到这一步，我们整块环境已经起来了。

其中，pom.xml 就是我们 Maven 新建项目的包管理配置文件，我们双击打开，内容如下：

![微信图片_20250911145259](java软件开发工具.assets/微信图片_20250911145259.jpg)

10.开始配置JDK：

   1. 点击主界面左上角的菜单图标，依次选择“File”-“Project Structrue”：

      ![微信图片_20250911145530](java软件开发工具.assets/微信图片_20250911145530.jpg)

      ![微信图片_20250911145536](java软件开发工具.assets/微信图片_20250911145536.jpg)

   2. 此时打开项目的配置页面，依次选择“Project”-“SDK”-下拉-“Add JDK”：

      ![微信图片_20250911145541](java软件开发工具.assets/微信图片_20250911145541.jpg)

   3. 在选择对话框上选择我们前面安装的 JDK 路径：

      ![微信图片_20250911145546](java软件开发工具.assets/微信图片_20250911145546.jpg)

   4. 选择“OK”按钮后，界面如下：

      ![微信图片_20250911145551](java软件开发工具.assets/微信图片_20250911145551.jpg)

   5. 此时会发现名称显示重复了加了一个序号，原因是自动识别的 JDK 重名了，我们点一下右边的“Edit”按钮编辑另外一个直观的名字：

      ![微信图片_20250911145555](java软件开发工具.assets/微信图片_20250911145555.jpg)

​    6. 最后选择“OK”进行保存，到这一步就已经配置完成了自定义 JDK 版本了。

​    7. 接下来再次测试一下上面测试工程的步骤，看下是否还能跑起来。

11.开始配置Maven：

   1. 点击主界面左上角的菜单图标，依次选择“File”-“Settings”：

      ![微信图片_20250911145929](java软件开发工具.assets/微信图片_20250911145929.jpg)

      ![微信图片_20250911145934](java软件开发工具.assets/微信图片_20250911145934.jpg)

   2. 此时打开全局设置页面，在地址栏上搜索：maven：

      ![微信图片_20250911145939](java软件开发工具.assets/微信图片_20250911145939.jpg)

   3. 依次参考上面圈出来的选项进入右侧页面，点一下“Maven home path”右边的选项按钮，然后定位到我们之前安装的 Maven 目录，选择“OK”，保存配置：

      ![微信图片_20250911145943](java软件开发工具.assets/微信图片_20250911145943.jpg)

   4. 此时会发现，Maven 识别的版本变成了我们安装的：

      ![微信图片_20250911145947](java软件开发工具.assets/微信图片_20250911145947.jpg)

   5. 最后别忘了点击页面的“OK”按钮保存配置使其生效：

      ![微信图片_20250911145952](java软件开发工具.assets/微信图片_20250911145952.jpg)

   6. 此时我们的 IDEA 会根据上面的 Maven 配置重新下载包：

      ![微信图片_20250911145957](java软件开发工具.assets/微信图片_20250911145957.jpg)

        7. 这个过程会比较久，等待片刻后，再次运行一下 Java 代码，看下正不正常即可。

12.关闭自动更新

1. 主界面菜单进入：“File”-“Settings”，这几项反选：

   ![微信图片_20250911150004](java软件开发工具.assets/微信图片_20250911150004.jpg)

   ![微信图片_20250911150009](java软件开发工具.assets/微信图片_20250911150009.jpg)

