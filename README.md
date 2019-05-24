# 🗺 ol3_turial  WebGIS on OpenLayers3
## 🙋‍简介 Introduction
这是一个使用OpenLayers3 API的教程/教学实例。本实例创建于2019年春。最新的基于ol5的教程将于2019年夏出版，老师👨‍🏫写的。

其中OL3DEMO为路网操作系统，可以对道路网进行查询、增加、删除等处理，使用Tomcat、GeoServer以及JQuery。

使用ol v3.20.1。

![OpenLayers](img/openlayers.png)
## ⏰当前进度 Current Progress
### ✔实现 Achievements
完成了一些关于地图控件的实现

- 上下左右的使用
- 更换地图源
- 更换画笔类型（点、线、面、圆）
- 显示当前层级、分辨率
- 实现了**不同页面**下的增删改查
    - 使用了GeoServer
    - 使用了jquery/zento
    - 使用了ol3
    - 使用了csdn作为参考


### ❓目前存在的问题 Problems&the problems u might meet

- ~~地图间距（估计加载< p >就好了）~~
    - 其实我还想要一个地图的装裱框
        - CSS文件也不错 margin？
        - 正在尝试使用antdesign
- ~~在设计地图联动之后，就没有办法绘制了~~
    - 修改了位置之后 就可以了（把var map2 设置在 script的最后面）
- 作业项目
    -  目前可以实现在本地的数据处理 
    -  目前正在整合文件 但是遇到了一些问题，估计是单个页面的某些函数之间的冲突
        - 解决方案为直接使用框架以及Frame 这样正好可以解决CSS的问题
    -  ~~但是现在好像没有前端没有连通服务器~~
        - 有以下两种情况
             - 根本没有发出去信息or信息有错误
             
             - 目前发现的是：
                 - 根本没有发出去信息——也就是说 我需要*审查代码*
                    - 仔细查阅控制台 终于发现了这个的操作方法
                            >
                                
                                <ows:ExceptionText>{http://geoserver.org/nyc_roads}nyc_roads is read-only</ows:ExceptionText>

                                
                            >
                        **readOnly**  太恐怖了

                - 也许与tomcat有关（重要的是设置跨域）
                - 也许与格式有关（其实这是最不容易坏掉的）
             - ~~geoserver坏掉了 ，需要检查报错~~

## 📕参考 My Reference
### OpenLayers基础与教学 How to start OpenLayers
没有相关基础的可以直接看这个👉 http://weilin.me/ol3-primer/ 

在test中的文件基本上完美复制了此教程 http://weilin.me/ol3-primer/ch12/12-01-02.html
### GeoServer 问题
#### 没有更新（权限为只读）
https://blog.csdn.net/wo_buzhidao/article/details/79268902 这个权当介绍出错的概念

https://blog.csdn.net/u013420816/article/details/54629158  这个在实际上解决了问题



## 💡重点 使用步骤 How to Show after finished

- 首先打开tomcat（使用cmd/iTerm2开启）
    - cd 到相应的位置（bin）
        -  C:\Dev\apache-tomcat-9.0.19\bin 
        -  ~/java/Tomcat/apache-tomcat-9.0.19/bin
    - startup.bat 或者 sh startup.sh
- 然后打开网页（http://localhost:8080/ol3/test/test.html）
- 就可以愉快的操作了
- 关闭/重启 需要配合 shutdown.sh 或者 .bat


# 👣重点 搭建步骤 How to Build & DownLoads
- 环境的搭建
    - [OpenLayers](https://openlayers.org/ "OpenLayers官网")
        - 这是实现拖动、缩放等控制显示功能 的库
    - [GeoServer](www.geoserver.org/ "官网")  
        - GeoServer is an open source server for sharing 
        geospatial data.
        - 自己去下载war文件，解压出war，然后拖到Tomcat的`WebAPPs`文件夹中即可
    - [Tomcat](http://tomcat.apache.org/ "官网" )
        - 一个免费的开放源代码的Web应用服务器
- 数据源的搭建（注意权限设置）
    - 下载
- 代码的搭建（一开始是直接复制粘贴的，但是后来看懂了）
- 点击F12进行测试 
  - 重点关注的 console （报错）
  - 还有就是 查看network中的XHR
