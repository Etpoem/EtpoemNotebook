# Pip Note
### 1. requirements.txt 中出现的 @file 引用自本地文件如何解决？
    pip list --format=freeze > requirements.txt
  
### 2. 配置国内镜像地址
    pip config set global.index-url https://mirrors.bfsu.edu.cn/pypi/web/simple
