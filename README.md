# IPsecVPNWithStrongswan
一键安装IPsec VPN，分别适用于搬瓦工VPS(OpenVZ)与DigitalOcean（KVM）

搬瓦工使用的文件为IPSecWithIKEV1SourceCode.sh

DO使用的文件为IPSecWithIKEV1Binary.sh

测试环境为

搬瓦工：Ubuntu 14.04 32位版本，内核版本为2.6.32-042stab102.9

DO：Ubuntu 14.04 64位版本，内核版本为3.13.0-48-generic x86_64

在文件修改/etc/ipsec.secrets部分中可自行定义PSK、账号和密码

在终端下运行

    cat /proc/sys/net/ipv4/ip_forward

若输出为1，则IPV4转发正常，否则修改/etc/sysctl.conf,搜索net.ipv4.ip_forward=1，去掉它的注释，保存后退出，执行sysctl -p，成功开启转发后，为文件添加执行权限后运行即可
