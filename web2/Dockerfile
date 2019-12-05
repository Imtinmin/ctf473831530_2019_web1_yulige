FROM ubuntu:16.04

RUN sed -i "s/http:\/\/archive.ubuntu.com/http:\/\/mirrors.aliyun.com/g" /etc/apt/sources.list
RUN apt-get update && apt-get install -y \
    python3  iputils-ping net-tools curl netcat-traditional \
    python3-pip

RUN pip3 install pip -i https://pypi.tuna.tsinghua.edu.cn/simple --upgrade
RUN sed -i "s/from pip import main/from pip._internal import main/g" /usr/bin/pip3
RUN sed -i "s/sys.exit(main())/sys.exit(main.main())/g" /usr/bin/pip3
RUN pip3 install flask -i https://pypi.tuna.tsinghua.edu.cn/simple
RUN echo "export HINT='mysql_user_is_yuligeeee123321'" >> /etc/profile
WORKDIR /var/www/yuligeeeeeee/
ADD ./app.py /var/www/yuligeeeeeee/
COPY ./start.sh /etc
RUN chmod u+x /etc/start.sh
RUN useradd -m ctf
RUN chown -R root:ctf /var/www/yuligeeeeeee/
RUN chmod -R 755 /var/www/yuligeeeeeee/

EXPOSE 8080

