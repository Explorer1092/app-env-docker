FROM openrasp/php5.6

MAINTAINER OpenRASP <ext_yunfenxi@baidu.com>

ENV install_url https://packages.baidu.com/app/wordpress-4.9.8-bin.tar.gz
ENV install_path /var/www/html


# 下载 
RUN cd /tmp \
	&& curl "$install_url" -o package.tar.gz \
	&& tar -zxf package.tar.gz -C "$install_path" \
	&& rm -f package.tar.gz \
	&& rm -f "$install_path"/www/install.php \
	&& chmod 777 -R "$install_path"

# 拷贝数据库文件
COPY database.sql /root/

# 更新启动脚本
COPY start.sh /root/
