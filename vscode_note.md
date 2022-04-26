## 1. 实现无密码远程登入
~~~bash
(1). 本机上生成密钥对
打开 cmd 键入 ssh-genkey 然后按下三次回车键
此时采用默认配置生成密钥对，会在 C:\Users\{your_name}\.ssh 目录下生成 私钥 id_ras 和公钥 id_ras.pub
如果上诉目录已存在相应文件则不用再次生成密钥对，ssh-keygen 命令详解可使用 ssh-keygen --help 查看

(2). 将公钥上传到远程机器
将 id_ras.pub 上传到远程机器的 ~/.ssh 目录下，若该目录不存在则创建之
cat id_rsa.pub >> authorized_keys
上诉命令会将 id_ras.pub 的内容追加到 authorized_keys
之后便可以吧 id_ras.pub 删掉
~~~
