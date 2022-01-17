---
layout: project_single
title:  "echo 0x01"
slug: "scripts"
---

Here are my one-liners that I often use in the scenarios. I call these [funny little helpers](https://github.com/AntiSecTech/AntiSecTech.github.io/blob/main/_project/scripts.md). You can then easily use this with copy and paste.

## Table of Content
### FLH - funny little helpers
- [my IP Address](#my-IP-Address)
- [Target IP Address](#Target-IP-Address)
- [check for SSH](#check-for-SSH)
- [check for HTTP](#check-for-HTTP)
- [get HTTP Header](#get-HTTP-Header)
- [HOSTS Entry](#HOSTS-Entry)
- [arp-scan](#arp-scan)
- [Portscan using Netcat](#Portscan-using-Netcat)
- [nmap-scan](#nmap-scan)

---

## my IP Address
```sh
export IP=$(ifconfig wlan0 | grep "inet " | awk '{print $2}')
```

## Target IP Address
```sh
export TIP=$(sudo arp-scan $RANGE | grep PCS | awk '{print $1}')
```
or use alternarives (like **arp-scan** or **netdiscover**)

## check for SSH
```sh
echo > /dev/tcp/$TIP/22; [ $? -eq 0 ] && echo 'SSH OPEN' || echo 'SSH CLOSED'
```

## check for HTTP
```sh
echo > /dev/tcp/$TIP/80; [ $? -eq 0 ] && echo 'HTTP Server running' || echo 'HTTP Server not running'
```

## get HTTP Header
```sh
printf "HEAD / HTTP/1.0\r\n\r\n" | nc $TIP 80
```
same like
```sh
curl -IL "http://$TIP"
```

## HOSTS Entry
however, this operation only works if you are generally operating as a super user.<br>
$THOST must be declared first, e.g. with ```export THOST=example.box```<br>
for checking ```echo $THOST```<br>
```sh
echo "${TIP} ${THOST}" >> /etc/hosts ; cat /etc/hosts | grep $THOST
```

## arp-scan
```sh
sudo arp-scan $RANGE | grep PCS | awk '{print $1}'
```

## Portscan using Netcat
a really primitive port scan that checks the range from 21 to 8080
```sh
nc -zv $TIP 21-8080
```

## nmap-scan
```sh
nmap -T4 -A -v $(sudo arp-scan $RANGE | grep PCS | awk '{print $1}')
```
or
```sh
nmap -T4 -A -v $(echo $TIP)
```
