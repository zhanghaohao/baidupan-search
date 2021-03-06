# baidupan-search
百度网盘搜索引擎，内置两种搜索引擎，实时搜索引擎和全文检索引擎，既适合用来做站点，同时也适合学习实践。
# 百度网盘简单介绍
百度网盘是个人网上硬盘，用户申请后可以获取大概10G的硬盘空间，用户上传文件至百度网盘后可以分享出去，这样别人只要有分享链接就可以看到内容了。  
其实这里面是存在安全隐患的，所以百度对上传文件对审核是非常严格的。  
由于百度网盘的用户量很大，所以上面分享的文件数量也很大，有很多有价值的文件可以为大家所用，所以才会诞生百度网盘搜索引擎这样的东东。  
本项目内部嵌入了几个百度网盘资源库，用户在输入关键字后，搜索引擎会实时对资源库进行爬取，然后把结果过滤，筛选后返回给用户。
# 架构设计
![image](https://raw.githubusercontent.com/zhanghaohao/pictures/master/百度网盘搜索引擎.png)
# 爬虫引擎
代码目录baidupan-search/src/crawlengine/resource/下内置了几个爬虫引擎，可以爬取网盘资源，想要学习用Golang写爬虫的同学可以借鉴下。
# 全文检索引擎
代码采用sphinx作为全文检索引擎，这款软件是俄罗斯人开发后开源的，非常轻量级，千万级记录索引后只消耗几百兆的内存，而且检索结果速度也很快，非常适合中小团队使用。
不像ElasticSearch，动辄就需要几个G的内存资源。
# 安装
## 开发环境配置
请先下载Golang语言的IDE，比如Goland。    
安装Go1.9以上版本。
## 安装依赖包
```
export GOPATH=xxxx
export GO111MODULE=off
export GOPROXY=https://goproxy.io
go mod vendor
```
## 修改配置文件
请根据你的情况修改配置文件：src/plugin/config/config.yaml。     
包含Mysql、Redis、微信服务号、Sphinx的配置。
## 启动程序
`cd src/`  
`go build start.go`
## 访问网站
程序跑起来后会在本地8080端口监听，你可以通过http://localhost:8080 来访问。
# 欢迎随时联系我
本人有多年运维开发经验，擅长Linux, Ansible, Kubernetes, Golang, Python, Html等技术。     
如果有小伙伴考虑创业或者私活，或者对我的项目感兴趣的可以随时联系我。     
本人邮箱：zhouxing_good@yeah.net     

