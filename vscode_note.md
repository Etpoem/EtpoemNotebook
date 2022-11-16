## 1. 实现无密码远程登入
~~~bash
(1). 本机上生成密钥对
打开 cmd 键入 ssh-genkey 然后按下三次回车键
此时采用默认配置生成密钥对，会在 C:\Users\{your_name}\.ssh 目录下生成 私钥 id_ras 和公钥 id_ras.pub
如果上诉目录已存在相应文件则不用再次生成密钥对，ssh-keygen 命令详解可使用 ssh-keygen --help 查看

(2). 将公钥上传到远程机器
将 id_ras.pub 上传到远程机器的 ~/.ssh 目录下，若该目录不存在则创建之，然后执行以下命令
cat id_rsa.pub >> authorized_keys
上诉命令会将 id_ras.pub 的内容追加到 authorized_keys
之后便可以把 id_ras.pub 删掉
~~~

## 2. vscode 远程开发环境变量配置
（1). VSCode Remote 登陆远程服务器时，使用的是 Interactive login 方式，这种方式会加载 /etc/profile, ~/.bash_profile, ~/.bash_login, ~/.profile 而不会加载 ~/.bashrc, 所以想要 VSCode 获取正确的环境变量， 要把环境变量写入 /etc/profile, ~/.bash_profile, ~/.bash_login, ~/.profile 之一。
（2). VSCode Remote的环境变量加载是在第一次远程服务器启动 Remote Server 时， 所以更改环境变量想要生效必须重启远程 Server, vscode 上键入 Ctrl + Shift + p ，然后搜索 Remote-SHH: Kill VSCode Server on host... 然后重新加载 vscode

