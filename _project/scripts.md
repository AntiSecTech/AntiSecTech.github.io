---
layout: project_single
title:  "echo 0x01"
slug: "scripts"
---

Here are my one-liners that I often use in the scenarios. I call these funny little helpers.

### arp-scan
```sh
sudo arp-scan $RANGE | grep PCS | awk '{print $1}'
```

### nmap-scan
```sh
nmap -T4 -A -v $(sudo arp-scan $RANGE | grep PCS | awk '{print $1}')
```
