### Connections sharing (using _wlan0_ as external interface):

    iptables -A FORWARD -o wlan0 -i eth0 -s 192.168.0.0/24 -m conntrack --ctstate NEW -j ACCEPT
    iptables -A FORWARD -m conntrack --ctstate ESTABLISHED,RELATED -j ACCEPT
    iptables -t nat -F POSTROUTING
    iptables -t nat -A POSTROUTING -o wlan0 -j MASQUERADE

#### Requires ip4forward:

    echo 1 > /proc/sys/net/ipv4/ip_forward

#### Source:

https://help.ubuntu.com/community/Internet/ConnectionSharing

put everything in /etc/rc.local

_don't remember why this is here, this is done by the_ ltspchroot -a _command_

add

    mount --bind /proc /opt/ltsp/amd64/proc
