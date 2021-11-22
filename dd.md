DD 重装

· 甲骨文
````
bash <(wget --no-check-certificate -qO- 'https://moeclub.org/attachment/LinuxShell/InstallNET.sh') -d 9 -v 64 -a -firmware
````


· 三毛
````
wget -N --no-check-certificate https://raw.githubusercontent.com/veip007/dd/master/dd-gd.sh && chmod +x dd-gd.sh && ./dd-gd.sh
````


· gcore
````
wget git.io/auto.sh
bash auto.sh -d 9 -v 64 -a -p 密码
````


· 轻量
````
bash <(wget --no-check-certificate -qO- 'https://moeclub.org/attachment/LinuxShell/InstallNET.sh') -d 10 -v 64 -a
````


以上内容来自这条帖子

· 带 WebUI 可查看进度的
````
https://raw.githubusercontent.com/flyqie/dd-shell/master/Core_Install.sh
````

国内机可使用
````
https://ghproxy.com/https://raw.githubusercontent.com/flyqie/dd-shell/master/Core_Install.sh
````

感谢 @flyqie 大佬 原帖地址

最近在使用 @insightfy 大佬的(不知道为啥萌咖大佬的我DD到11 貌似没成功过这个大佬的可以)  帖子地址
````
bash <(wget --no-check-certificate -qO- 'https://file.geekn.net/CNODnjau/InstallNET.sh') -d 11 -v 64 -a -firmware
````


目前我所知道的一些参数（可能有的不准确，欢迎大佬指出）
````
-firmware  额外的驱动支持
-d             后面是系统版本号
-v             后面写64位 32位
-a             （不清楚这个干啥的但是每个脚本都带）
--mirror     后面是镜像源地址
````

-p             后面写自定义密码
````
镜像站地址
官方给出的地址列表：https://www.debian.org/mirror/list

一些国内的
ftp.cn.debian.org
mirror.bjtu.edu.cn
mirror.lzu.edu.cn       
mirror.nju.edu.cn       
mirrors.163.com       
mirrors.bfsu.edu.cn       
mirrors.hit.edu.cn       
mirrors.huaweicloud.com       
mirror.sjtu.edu.cn       
mirrors.tuna.tsinghua.edu.cn       
mirrors.ustc.edu.cn       

使用方法：（大致都是一样的）


清华源
--mirror 'https://mirrors.ustc.edu.cn/debian/'

腾讯源
--mirror 'https://mirrors.aliyun.com/debian/'

阿里源
--mirror 'https://mirrors.aliyun.com/debian/'

华为源
--mirror 'https://mirrors.huaweicloud.com/debian/'

````


宝塔面板&AApanel
````
Debian系统
# 宝塔
wget -O install.sh http://download.bt.cn/install/install-ubuntu_6.0.sh && bash install.sh

# aapanel
wget -O install.sh http://www.aapanel.com/script/install-ubuntu_6.0_en.sh && bash install.sh

````


有次无聊看了看文件发现aapanel就是宝塔的换皮，语言换成了英语，所以破解方法一样。
````
# 宝塔去实名认证
rm -rf /www/server/panel/data/bind.pl

# 宝塔&aapanel破解
编辑 /www/server/panel/class/panelplugin.py
找到 softList['list'] = tmpList 这行代码
在下面添加以下代码，注意缩进

softList['pro'] = 1
for soft in softList['list']:
soft['endtime'] = 0

编辑完毕后保存重启面板即可
````


常用脚本
````
一键开启BBR
echo "net.core.default_qdisc=fq" >> /etc/sysctl.conf
echo "net.ipv4.tcp_congestion_control=bbr" >> /etc/sysctl.conf
sysctl -p
sysctl net.ipv4.tcp_available_congestion_control
lsmod | grep bbr
````


superbench
````
wget -qO- git.io/superbench.sh | bash
````

````
Bench.sh
wget -qO- bench.sh | bash
````


三网测速
````
bash <(curl -Lso- http://yun.789888.xyz/speedtest.sh)
````


流媒体
````
#第一个
bash <(curl -L -s https://raw.githubusercontent.com/lmc999/RegionRestrictionCheck/main/check.sh)

# 第二个
bash <(curl -sSL "https://github.com/CoiaPrant/MediaUnlock_Test/raw/main/check.sh")
````


回程
````
# 第一个
wget https://raw.githubusercontent.com/nanqinlang-script/testrace/master/testrace.sh
bash testrace.sh

# 第二个
wget -qO- git.io/besttrace | bash
````


国内机一件安装docker
````
curl -sSL https://get.daocloud.io/docker | sh
````

卸载docker
````
sudo apt-get remove docker docker-engine
rm -fr /var/lib/docker/
````

国内机安装docker-compose
````
curl -L https://get.daocloud.io/docker/compose/releases/download/v2.1.1/docker-compose-`uname -s`-`uname -m` > /usr/local/bin/docker-compose
chmod +x /usr/local/bin/docker-compose
````
