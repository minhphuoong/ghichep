# Cấu hình IPv6 trên CentOS  #

### Bước 1: ###

Mở file:


    # vi /etc/sysconfig/network

Thêm nội dung:


    NETWORKING_IPV6=yes


### Bước 2 ###

Mở file:


    # vi /etc/sysconfig/network-scripts/ifcfg-eth0


Thêm nội dung sau:


	IPV6INIT=yes
	IPV6ADDR=<IPv6-IP-Address>
	IPV6_DEFAULTGW=<IPv6-IP-Gateway-Address>


### Bước 3 ###

Khởi động lại network:

    # service network restart

Kiểm tra:

    [root@phuongcentos68543 ~]# ip a
    1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN 
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
    inet6 ::1/128 scope host 
       valid_lft forever preferred_lft forever
    2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc pfifo_fast state UP qlen 1000
    link/ether 00:0c:29:e6:bf:be brd ff:ff:ff:ff:ff:ff
    inet 210.245.85.43/24 brd 210.245.85.255 scope global eth0
    inet6 2405:4800:200:5005::8/64 scope global 
       valid_lft forever preferred_lft forever
    inet6 fe80::20c:29ff:fee6:bfbe/64 scope link 
       valid_lft forever preferred_lft forever

    [root@phuongcentos68543 ~]# ping6 2001:4860:4860::8888 
    PING 2001:4860:4860::8888(2001:4860:4860::8888) 56 data bytes
    64 bytes from 2001:4860:4860::8888: icmp_seq=1 ttl=60 time=19.9 ms
    64 bytes from 2001:4860:4860::8888: icmp_seq=2 ttl=60 time=19.9 ms
    64 bytes from 2001:4860:4860::8888: icmp_seq=3 ttl=60 time=19.9 ms


