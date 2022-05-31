## 1. docker 内开启 ssh 服务，使用 vscode 进行远程开发
~~~bash
docker exec -it ${contain_name} bash
# 生成 root 密码， 用于登陆使用
passwd 
sed -i s/archive.ubuntu.com/mirrors.aliyun.com/g /etc/apt/sources.list
sed -i s/security.ubuntu.com/mirrors.aliyun.com/g /etc/apt/sources.list
apt update -y 
# vim 用于修改配置， wget 用于远程登陆时下载 vscode
apt install -y --no-install-recommends vim openssh-server wget

vi /etc/ssh/sshd_config
# 修改 sshd server 的配置
# 1.去除 Port 的注释，并修改为希望ssh服务运行的端口，这里要避免和本机 22 端口冲突，可修改为 10322 等
# 2.去除 PermitRootLogin 注释,并改为 yes，允许 root 账号用密码远程登陆

mkdir -p /var/run/sshd
/usr/sbin/sshd -D &

~~~
