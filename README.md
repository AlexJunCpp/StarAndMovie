# StarAndMovie
“超级明星脸”是一款基于深度学习的微信小程序，能够根据用户的上传照片匹配最相似的明星，推荐明星主演的电影。

# 前言
“超级明星脸”是一款基于人脸相似度为用户推荐电影的微信小程序。整个系统分为前端展示、人脸识别、Web服务器架构和数据库四个模块。其中，样本库中共计97位明星，这些明星来自于7、8月份的暑期热映电影和其它较受欢迎的电影。  

# 演示
![](https://note.youdao.com/yws/api/personal/file/0FB8981B8ABE4B149F131C0C44AB553B?method=download&shareKey=9385dd9d99911bc2f0248b510ea5d9dd)  
# 方式
微信内搜索“超级明星脸”或者扫描下方二维码即可体验  
![](https://note.youdao.com/yws/api/personal/file/F6068E051CA2417EB37CB7CF2C145381?method=download&shareKey=1aeff6d2cbb60b42222a3787da8793a3)
#### 喜欢的请点STAR FORK 给个支持~~

# 进度
项目开发周期为1个月：
 - 第1-2周：完成小程序的前端实现、后端代码及数据库设计、服务器搭建等工作；
 - 第3周：与人脸检测模块进行代码整合及连调；
 - 第4周：完成测试工作和发布上线，重点实现用户的并发访问和性能调优。
# 目标
(已实现)
1. 小程序前端设计与实现  
   - 提供用户图片上传服务，并实时展示最像明星及具体信息
   - 能够根据检测出的最像明星，展示明星的近期作品及剧情简介
2. 后端及数据库的实现 
   - 支持前后端分离，对用户上传的图片进行接收处理并返回结果
   - 能够存储明星的作品信息以及用户的相关信息
1. 支持多用户的良好体验
   - 支持多进程和多线程的方式启动程序，监控程序的运行状态
   - 服务器能够实现高性能和低内存占用率    
   
# 流程
![流程图](https://note.youdao.com/yws/api/personal/file/6EE7AA4ACF42431EB5BC89BB18B6EA91?method=download&shareKey=abba9b66db6a5750b8c00eeb8eb072ba "流程图")  
详细过程如图所示，图中虚线部分已全部部署在华为云服务器上。
1. 用户点击“开始测一测”按钮，上传手机相册内的照片或选择拍照;
1. 在Web后端程序中，将用户上传的照片保存至服务器，同时，发送用户照片地址到人脸检测模块；
1. 调用人脸检测封装好的类，获取与用户上传照片最相似的明星姓名和照片地址；
1. 根据明星姓名，在数据库中搜索查找明星相关的电影信息；
1. 返回4)步查询结果，明星参演的电影名称和剧情简介；
1. 将5)步查询结果，以及用户照片与明星相似度指数、明星照片等信息，一同返回前端进行展示；  

# 技术
**人脸检测模块**
   - from  给力小伙伴纯手写“人脸检测和匹配的最相似明星”代码 
   
**前端（微信小程序开发语言）：**
   - WXML
   - WXSS
   - JS    
   - 两个页面（index和logs文件）
   ![前端代码结构](https://note.youdao.com/yws/api/personal/file/152A7F82F54E4A008BD8FA524DF10C3E?method=download&shareKey=fe968b41d67e568720a1c9de98d3c313 "前端代码结构")  
   
**后端及Web服务器架构：**
   - Nginx + uWSGI + Django  
   - 数据库：splite3
![Web服务器架构](https://note.youdao.com/yws/api/personal/file/623C658F9AA648598931D8D68A37E31B?method=download&shareKey=9a5b343424936930333f0fcafb507882 "Web服务器架构")

