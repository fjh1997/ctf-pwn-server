在当前目录按以下方式创建环境<br>
1.修改题目bin目录下的flag内容和pwn内容<br>
2.修改dockerfile里的ubuntu为你想要的版本<br>
3.修改docker-compose.xml里的端口，运行以下命令<br>
```bash
sudo docker compose up -d
```
如果是ubuntu 19以上（包括19）的镜像，请将Dockerfile
```bash
RUN cp -R /lib* /home/ctf && \
    cp -R /usr/lib* /home/ctf
```
改为
```bash
RUN cp -R /usr/lib* /home/ctf
```
原因是ubuntu19以上采用了软连接模式。/lib*只是一个软链接

