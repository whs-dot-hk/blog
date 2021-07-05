---
title: "5 Things to Do After Installing Clear Linux [1/5]"
date: 2021-07-05T21:02:46+08:00
tags:
  - Clear Linux
  - Linux
  - Firewall
  - iptables
  - Security
  - Swupd
---
You should first enable [firewall][clear linux firewall documentation] for both IPv4 and IPv6.

```sh
# Install iptables bundle
sudo swupd bundle-add iptables
# Set ipv4 rules
sudo iptables -P INPUT DROP
sudo iptables -P FORWARD DROP
sudo iptables -P OUTPUT ACCEPT
sudo iptables -A INPUT -i lo -j ACCEPT
sudo iptables -A OUTPUT -o lo -j ACCEPT
sudo iptables -A INPUT -m conntrack --ctstate ESTABLISHED,RELATED -j ACCEPT
sudo systemctl start iptables-save
sudo systemctl enable iptables-restore.service
# Set ipv6 rules
sudo ip6tables -P INPUT DROP
sudo ip6tables -P FORWARD DROP
sudo ip6tables -P OUTPUT ACCEPT
sudo ip6tables -A INPUT -i lo -j ACCEPT
sudo ip6tables -A OUTPUT -o lo -j ACCEPT
sudo ip6tables -A INPUT -m conntrack --ctstate ESTABLISHED,RELATED -j ACCEPT
sudo systemctl start ip6tables-save
sudo systemctl enable ip6tables-restore.service
```

[clear linux firewall documentation]: https://docs.01.org/clearlinux/latest/guides/network/firewall.html#iptables
