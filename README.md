### 获取Root权限，可改root密码的一键脚本

支持root或非root模式下运行，个别系统只能在root模式下运行。

脚本集成获取最高权限属性（以防止被暴力破解后改属性造成无法修改root密码），自动识别VPS是否支持获取Root权限，是否可更改root密码

后续再次执行脚本意味着更改root密码！！

一键脚本：

```
bash <(curl -sSL https://cdn.jsdelivr.net/gh/suxihui/root/root.sh)
```
```
bash <(curl -sSL https://raw.githubusercontent.com/suxihui/root/main/root.sh)
```
用户名：root，密码必须自定义。

登录SSH时，请更改原用户名为root，并输入自定义密码！


开放所有端口:
```
iptables -P INPUT ACCEPT
iptables -P FORWARD ACCEPT
iptables -P OUTPUT ACCEPT
iptables -F
```
关闭防火墙:
```
systemctl stop firewalld.service && systemctl disable firewalld.service
```


Docker安装:
```
sudo yum check-update
curl -fsSL https://get.docker.com/ | sh
sudo systemctl start docker
sudo systemctl status docker
sudo systemctl enable docker
```
停止所有的容器
```
docker stop $(docker ps -a -q)
```

删除所有的容器
```
docker rm $(docker ps -a -q)
```

删除全部的images
```
docker rmi $(docker images -q)
```

删除文件夹ql
```
rm -rf ql
```

