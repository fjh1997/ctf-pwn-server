
# pwn server
 A easy ctf pwn challenge environment <br>
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

In the current directory, create an environment as follows:  

1. Modify the contents of the `flag` file and the `pwn` file under the `bin` directory.  
2. Change the version of Ubuntu in the `Dockerfile` to your desired version.  
3. Modify the port in `docker-compose.xml`, then run the following command:  
```bash
sudo docker compose up -d
```  

If you are using an Ubuntu image version 19 or later (including 19), update the `Dockerfile` as follows:  
Replace:  
```bash
RUN cp -R /lib* /home/ctf && \
    cp -R /usr/lib* /home/ctf
```  
With:  
```bash
RUN cp -R /usr/lib* /home/ctf
```  

The reason is that Ubuntu 19 and later versions use a symlinked structure, where `/lib*` is just a symbolic link.
