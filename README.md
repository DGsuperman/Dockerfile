# centos_nginx_php5
> **centos_nginx_php5** 基础镜像为 **centos7** 且安装了**nginx**与**php**环境
> 目录中的code是来自github的html小游戏
> 运行容器后通过浏览器访问宿主机IP
### 生成并运行容器
``` bash
cd centos_nginx_php5
# 生成Docker镜像
docker build -t c7_nginx_p5 .
# 运行docker容器
docker run -itd --name c7_web1 -p 80:80 c7_nginx_p5 
```
