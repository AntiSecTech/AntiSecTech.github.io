---
layout: project_single
title:  "echo 0x01"
slug: "scripts"
---

Here are my one-liners that I often use in the scenarios. I call these funny little helpers.

### my IP Address
```sh
export IP=$(ifconfig wlan0 | grep "inet " | awk '{print $2}')
```

### Target IP Address
```sh
export TIP=$(sudo arp-scan $RANGE | grep PCS | awk '{print $1}')
```
or use alternarives (like **arp-scan** or **netdiscover**)

### HOSTS Entry
however, this operation only works if you are generally operating as a super user.<br>
$THOST must be declared first, e.g. with ```export THOST=example.box```<br>
for checking ```echo $THOST```<br>
```sh
echo "${TIP} ${THOST}" >> /etc/hosts ; cat /etc/hosts | grep $THOST
```

### arp-scan
```sh
sudo arp-scan $RANGE | grep PCS | awk '{print $1}'
```

### nmap-scan
```sh
nmap -T4 -A -v $(sudo arp-scan $RANGE | grep PCS | awk '{print $1}')
```
or
```sh
nmap -T4 -A -v $(echo $TIP)
```
