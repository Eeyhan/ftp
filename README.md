# ftp

* 利用python做的ftp服务，实现ftp服务管理，利用队列限制并发量
* 本项目仅测试使用，需要再加功能可二次开发


## 开发环境：

* python3
* thread

## 功能简介：


* 用户加密认证
* 利用thread线程池允许同时多用户登录，允许配置最大并发数
* 每个用户有自己的家目录 ，且只能访问自己的家目录
* 对用户进行磁盘配额，每个用户的可用空间不同
* 允许用户在ftp server上随意切换目录
* 允许用户查看当前目录下文件
* 允许上传和下载文件，保证文件一致性(md5)
* 文件传输过程中显示进度条

* 支持的操作命令：
	+ 下载文件：get  文件名
	+ 上传文件：put  文件名
	+ 进入目录：cd  目录名
	+ 以及基本的终端命令
* 支持文件的断点续传

## 文件结构：

.
+ ├─.idea
+ │  └─inspectionProfiles
+ ├─client
+ │  └─__pycache__
+ │  └─boot_client.py  # ftp客户端执行文件
+ └─server
+     ├─bin
+ 	  │ └─boot_server.py # ftp服务端执行文件
+     ├─conf
+     │  └─__pycache__
+     │  └─settings.py	# 配置文件
+     ├─db
+  	  │  └─.userdata 	# 用户数据库
+     ├─FTP_workstation # 工作区
+     │  ├─jack
+     │  │  └─test
+     │  │      └─one
+     │  ├─nero
+     │  └─zaki
+     ├─lib
+     │  └─client	# 客户端
+  	  │  └─load_dump_data	# 数据中转文件
+     │  └─logger.py	# 日志文件
+     │  └─servers.py	# 服务端主程序文件
+     ├─log
+     └─client.log	# 客户端登录日志
+     └─server.log	# 服务端登录日志

## 启动：

* 先启动boot_server.py文件
* 再启动boot_client.py文件






