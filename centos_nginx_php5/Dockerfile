# 使用centos:7镜像
FROM centos:7

# 安装配置nginx、supervisor、php
COPY nginx-1.10.0-1.el7.ngx.x86_64.rpm /tmp/
RUN yum install epel-release openssl php-fpm php-mbstring php-gd -y &&\
	yum install supervisor -y &&\
	rpm -ivh /tmp/nginx-1.10.0-1.el7.ngx.x86_64.rpm &&\
	rm -f /tmp/nginx-1.10.0-1.el7.ngx.x86_64.rpm &&\
	yum clean all

COPY default.conf /etc/nginx/conf.d/default.conf
COPY nginx_php.ini /etc/supervisord.d/
COPY supervisord.conf /etc/supervisord.conf
	

# 导入源码
ADD code.tar.gz /usr/share/nginx/html/
RUN mv /usr/share/nginx/html/code/* /usr/share/nginx/html/ &&\
        rm -rf /usr/share/nginx/html/code/


# 暴露端口
EXPOSE 80

CMD ["/usr/bin/supervisord","-c","/etc/supervisord.conf"]


