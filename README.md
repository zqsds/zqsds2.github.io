# zqsds2.github.io
使用hexo建站


# yum ss

1、aws服务器选择

    创建aws实例网址:https://ap-northeast-2.console.aws.amazon.com/ec2/home?region=ap-northeast-2#Instances:
    实例类型: t2.micro
    AMI:Amazon Linux 2 AMI (HVM) - Kernel 5.10, SSD Volume Type
    安全组设置:出入站规则开放端口号 自定义 TCP	TCP 22381 ->0.0.0.0/0	

2、aws服务器安装ss的命令

    yum install -y https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
    yum makecache
    sudo yum update && sudo yum upgrade -y
    sudo modprobe tcp_bbr
    echo "tcp_bbr" >> /etc/modules-load.d/modules.conf
    echo "net.core.default_qdisc=fq" >> /etc/sysctl.conf
    echo "net.ipv4.tcp_congestion_control=bbr" >> /etc/sysctl.conf
    sudo sysctl -p
    lsmod | grep bbr
    wget --no-check-certificate -O shadowsocks-all.sh https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks-all.sh
    chmod +x shadowsocks-all.sh
    ./shadowsocks-all.sh 2>&1 | tee shadowsocks-all.log

1.  配置ss
    

*   选择python版本
    
*   设置密码
    
*   设置端口号
    
*   设置加密方式:chacha20-ietf-poly1305
