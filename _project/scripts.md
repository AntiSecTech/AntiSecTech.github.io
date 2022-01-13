---
layout: project_single
title:  "echo 0x01"
slug: "scripts"
---

Here are my one-liners that I often use in the scenarios.

### arp-scan
```sh
sudo arp-scan $RANGE | grep PCS | awk '{print $1}'
```
