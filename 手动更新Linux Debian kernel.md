# 对于debian系统
```
echo "deb http://ftp.debian.org/debian stretch-backports main" | tee -a /etc/apt/sources.list > /dev/null
apt-get update
apt-get install aptitude
aptitude search linux-image
apt-get -t stretch-backports upgrade

#对于dp0-9 以下方法不可用，提示dp0-9 uninstallable
#apt-get install -t stretch-backports linux-image-amd64 linux-headers-amd64

需要使用：
apt-get -t stretch-backports install linux-image-4.19.0-0.bpo.8-amd64 linux-headers-4.19.0-0.bpo.8-amd64 firmware-linux-free
```

# 对于Ubuntu系统，将内核版本升级到4.19的方法：

```
1.查看当前版本
  cat /proc/version
  uname -r
2.下载内核
  sftp -p 120 root@198.X.X.X
  or
  wget http://kernel.ubuntu.com/~kernel-ppa/mainline/v4.19/linux-headers-4.19.0-041900_4.19.0-041900.201810221809_all.deb \
  wget http://kernel.ubuntu.com/~kernel-ppa/mainline/v4.19/linux-headers-4.19.0-041900-generic_4.19.0-041900.201810221809_amd64.deb \
  wget http://kernel.ubuntu.com/~kernel-ppa/mainline/v4.19/linux-image-unsigned-4.19.0-041900-generic_4.19.0-041900.201810221809_amd64.deb \
  wget http://kernel.ubuntu.com/~kernel-ppa/mainline/v4.19/linux-modules-4.19.0-041900-generic_4.19.0-041900.201810221809_amd64.deb
  
3.安装内核
  sudo dpkg -i *.deb
  
4.重启
  sudo reboot
```
