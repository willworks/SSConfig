# SSConfig
shadowsocks config on ubuntu

 - sudo apt-get update

 - sudo python --version

 - apt-get install python-gevent python-pip

 - pip install shadowsocks

 - 找到shadowsocks文件夹的命令： sudo find / -name shadows* ("/"是根目录下， *是通配符)

 - 修改config.js
{
	"server":"127.0.0.1",
	"server_port":8388,
	"local_port":10808,
	"password":"密码",
	"timeout":600,
	"method":"aes-256-cfb"
}


 - 后台长期启动shadowsockts

 nohup ssserver -c /usr/local/lib/python2.7/dist-packages/shadowsocks/config.json > log &

 - 查看后台启动任务

 jobs

 - 开机自动启动

 cd /etc/
 sudo vim rc.local
 加上一行：/usr/local/bin/ssserver -c /usr/local/lib/python2.7/dist-packages/shadowsocks/config.json

  

 - 配置客户端：
{
	"server":"服务器ip",
	"server_port":8388,
	"local_port":10808,
	"password":"密码",
	"timeout":600,
	"method":"aes-256-cfb"
}