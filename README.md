########################
centos_nginx_php5
是基于docker写的Dockerfile
基础镜像为centos7 安装了nginx与php环境
文件中的code是来自github的html小游戏
生成镜像：
cd centos_nginx_php5
docker build -t c7_nginx_p5 .
运行容器
docker run -itd --name c7_web1 -p 80:80 c7_nginx_p5 
确保宿主机80端口不被占用
浏览器访问宿主机IP
