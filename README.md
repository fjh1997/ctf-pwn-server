在当前目录按以下方式创建环境
1.修改题目bin目录下的flag内容和pwn内容
2.修改dockerfile里的ubuntu为你想要的版本
3.运行以下命令，port替换为你想映射到的本机端口
```bash
sudo docker build -t "pwn" .
sudo docker run -d -p "0.0.0.0:port1:9999" -h "pwn" --name="pwn" --restart=always pwn 
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

