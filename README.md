# TCP-BBR
Auto install latest kernel for TCP BBR

### 系统支持

CentOS 6+/Debian 7+/Ubuntu 12+

### 虚拟技术

OpenVZ 以外的，比如 KVM、Xen、VMware 等

### 内存要求

RAM≥128M

### 使用方法

使用root用户登录，运行以下命令：

    wget --no-check-certificate https://github.com/teddysun/across/raw/master/bbr.sh
    chmod +x bbr.sh
    ./bbr.sh
    
安装完成后，脚本会提示需要重启 VPS，输入 y 并回车后重启。
重启完成后，进入 VPS，验证一下是否成功安装最新内核并开启 TCP BBR，输入以下命令：

    uname -r

查看内核版本，含有 4.12 就表示 OK 了

    sysctl net.ipv4.tcp_available_congestion_control
    
返回值一般为：
net.ipv4.tcp_available_congestion_control = bbr cubic reno

    sysctl net.ipv4.tcp_congestion_control
    
返回值一般为：
net.ipv4.tcp_congestion_control = bbr

    sysctl net.core.default_qdisc
    
返回值一般为：
net.core.default_qdisc = fq

    lsmod | grep bbr
    
返回值有 tcp_bbr 模块即说明bbr已启动。