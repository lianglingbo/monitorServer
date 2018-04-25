# monitorServer
实现功能：
	1.统计设备耗能总量（按类型区分）
	2.统计设备离线率
druid服务启动命令：
	
	1.启动imply主服务
		bin/supervise -c conf/supervise/quickstart.conf
	2.启动实时接收json的服务
		bin/tranquility server -configFile conf-quickstart/tranquility/dataserver2.json
	3.发送json的格式
		curl -H "Content-Type: application/json" -X POST  --data '{ "type":"3100", "sumdata":"39.22", 		"datetime":"1524188306000"}' http://192.168.31.26:8202/v1/post/haoneng
	4.启动superset
		进入虚拟环境
		. ./venv/bin/activate
 		启动superset
		superset runserver