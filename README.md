## dockerfiles

### SSH
用root權限登入\
apt-get install ssh\
vi /etc/ssh/sshd_config\
PermitRootLogin yes\
/etc/init.d/ssh  restart
 
### docker
安裝docker\
wget -qO- https://get.docker.com/ | sh
 
### 撰寫dockerfile
下載 dockerfile\
https://hub.docker.com/_/ubuntu/
 
### python
RUN apt-get update \
&& apt-get install -y python3 python3-pip wget \
&& pip3 install --upgrade pip 
 
### 爬蟲工具
&& pip3 install requests \
&& pip3 install beautifulsoup4 \
&& pip3 install selenium \
&& wget https://bitbucket.org/ariya/phantomjs/downloads/phantomjs-2.1.1-linux-x86_64.tar.bz2 \
&& tar -xvf phantomjs-2.1.1-linux-x86_64.tar.bz2 \
&& rm phantomjs-2.1.1-linux-x86_64.tar.bz2 \
&& mv phantomjs-2.1.1-linux-x86_64 /usr/local/share/ \
&& ln -s /usr/local/share/phantomjs-2.1.1-linux-x86_64/bin/phantomjs /usr/local/bin/phantomjs \
&& apt-get -y install libfontconfig
 
### 編碼問題
方法1：增加環境參數至dockerfile\
ENV LANG=C.UTF-8
 
方法2：在py檔加入\
import sys\
import io\
sys.stdout = io.TextIOWrapper(sys.stdout.buffer, encoding='utf-8')
 

