# ol3_turial
## 简介
这是一个使用OpenLayers3 API的教程/教学实例。本实例创建于2019年春。最新的基于ol5的教程将于2019年夏出版。

使用ol v3.20.1。

## 当前进度
### 实现
实现了一些关于地图控件的实现

- 上下左右的使用
- 更换地图源
- 更换画笔类型（点、线、面、圆）
- 显示当前层级、分辨率
- 实现了不同页面下的增删改查
    - 使用了GeoServer
    - 使用了jquery/zento
    - 使用了ol3
    - 使用了csdn作为参考

### 目前存在的问题

- ~~地图间距（估计加载< p >就好了）~~
    - 其实我还想要一个地图的装裱框
        - CSS文件也不错 margin？
- ~~在设计地图联动之后，就没有办法绘制了~~
    - 修改了位置之后 就可以了（把var map2 设置在 script的最后面）
- 作业项目
    -  目前可以实现在本地的数据处理 
    - 但是现在好像没有前端没有连通服务器
        - 有以下两种情况
             - 根本没有发出去信息/信息有错误

             - 目前发现的是：
                 - 根本没有发出去信息——也就是说 我需要*审查代码*
                    - 仔细查阅控制台 终于发现了这个的操作方法
                >
                    
                    <ows:ExceptionText>{http://geoserver.org/nyc_roads}nyc_roads is read-only</ows:ExceptionText>

                    readOnly 太恐怖了
                >
                  
                - 也许与tomcat有关
                - 也许与格式有关
             - geoserver坏掉了 ，需要检查报错

## 参考
http://weilin.me/ol3-primer/ 

http://weilin.me/ol3-primer/ch12/12-01-02.html

https://blog.csdn.net/wo_buzhidao/article/details/79268902 这个权当介绍出错的概念

https://blog.csdn.net/u013420816/article/details/54629158  这个在实际上解决了问题


