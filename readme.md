### Node use docker
- (http://www.07net01.com/2017/05/1858231.html)参考学习地址
— 创建Dockerfile文件
```javascript
FROM node:7-alpine

WORKDIR /app
ADD . /app
RUN npm install

ENTRYPOINT ["./entrypoint.sh"]
CMD ["start"]
```

- 执行构建命令
```javascript
docker build -t node-wlt .
```
说明node-wlt为镜像名，可以自己取名

- 如何保存镜像
```javascript
docker save 6c8196ccb3a1 >/Users/luyaoyuan/work1/node-wlt.tar
```
### Docker 经常使用的命令

- Ship-运输镜像（从仓库和我们的主机上运输）- 码头 - 仓库

- Run- 运行镜像（运行的镜像就是一个容器） - 运行程序的地方 - 容器

- Docker运行过程:去仓库把镜像拉倒本地，然后用一条命令把镜像运行起来变成容器！

- docker images  //查看本机的镜像
- docker pull hello-world   //添加到镜像仓库
- docker run hello-world  //运行镜像
- docker ps //查看本机运行的镜像
- docker run -d 镜像地址 //后台方式运行
- docker exex --help  //进入镜像内容
- docker run -d -p 8080:80 镜像地址  //与主机建立映射
- netstat -ng|grep 8080

### 说明
- ifconfig   //查看本机的ip地址

- REPOSTTORY  ： 镜像名字

- TAG  ： 版本（lastest 最新版）

- IMAGE ID  ：  64 位的字符串，可以唯一标识镜像，这里只显示16位，后面的被截掉了。

- CREATED ： 创建时间 （最后修改时间）

- SIZE ： 大小
