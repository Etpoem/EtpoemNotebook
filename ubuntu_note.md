# Ubuntu Note

## 1. 禁止内核自动更新
~~~bash
sudo apt-mark hold linux-image-generic linux-headers-generic

修改 /etc/apt/apt.conf.d 下的 10periodic 和 20auto-upgrades
将 1 全部改为 0
~~~
