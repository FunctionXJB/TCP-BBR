# TCP-BBR
Auto install latest kernel for TCP BBR

### ϵͳ֧��

CentOS 6+/Debian 7+/Ubuntu 12+

### ���⼼��

OpenVZ ����ģ����� KVM��Xen��VMware ��

### �ڴ�Ҫ��

RAM��128M

### ʹ�÷���

ʹ��root�û���¼�������������

    wget --no-check-certificate https://github.com/teddysun/across/raw/master/bbr.sh
    chmod +x bbr.sh
    ./bbr.sh
    
��װ��ɺ󣬽ű�����ʾ��Ҫ���� VPS������ y ���س���������
������ɺ󣬽��� VPS����֤һ���Ƿ�ɹ���װ�����ں˲����� TCP BBR�������������

    uname -r

�鿴�ں˰汾������ 4.12 �ͱ�ʾ OK ��

    sysctl net.ipv4.tcp_available_congestion_control
    
����ֵһ��Ϊ��
net.ipv4.tcp_available_congestion_control = bbr cubic reno

    sysctl net.ipv4.tcp_congestion_control
    
����ֵһ��Ϊ��
net.ipv4.tcp_congestion_control = bbr

    sysctl net.core.default_qdisc
    
����ֵһ��Ϊ��
net.core.default_qdisc = fq

    lsmod | grep bbr
    
����ֵ�� tcp_bbr ģ�鼴˵��bbr��������