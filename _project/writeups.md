---
layout: project_single
title: "writeups - walkthroughs"
slug: "writeups"
---

## initiation
normally i'm not the type of person who writes reports or writeups because my notes are generally in json format and contain all interesting information in plain text, e.g.
```json
[
    {
        "ATTACKER" : {
            "Nickname" : "bitcracker",
            "Userrank" : "Nobody",
            "Username" : "unknown",
            "Hostname" : "pentest",
            "Domainname" : "lab"
        },
        "TARGET" : {
            "Solved" : "2022-01-01",
            "Boxname" : "Example",
            "Creator" : "MySelf",
            "Level" : "EASY",
            "Release Date" : "2022-01-01",
            "MD5" : "ddce269a1e3d054cae349621c198dd52",
            "Environment" : "Virtualbox",
            "IPv4 Address" : "192.168.0.55",
            "MAC Address" : "3c:5a:b4:1a:0f:2b",
            "Hostname" : "example",
            "Domainname" : "box"
        },
        "PORTS" : {
            "SERVICE_INFO" : {
                "OS" : "Unix, Linux; CPE: cpe:/o:linux:linux_kernel"
            },
            "22/tcp" : [
                {
                    "SERVICE" : "ssh",
                    "VERSION" : "OpenSSH 7.9p1 Debian 10+deb10u2 (protocol 2.0)"
                }
            ],
            "80/tcp" : [
                {
                    "SERVICE" : "http",
                    "VERSION" : "Apache httpd 2.4.38 ((Debian))"
                }
            ]
        },
        "PWNED" : {
            "00" : [
                {
                    "Username" : "nobody",
                    "Password" : "chuckles79"
                }
            ]
        },
        "USERFLAG" : {
            "FLAG" : "dGhpcy5VU0VSW0ZMQUdd"
        },
        "ROOTFLAG" : {
            "FLAG" : "dGhpcy5ST09UW0ZMQUdd"
        }
    }
]
```
In most cases, however, this form of representation does not correspond to the rules of the common platforms that I use.<br>

Anonymization of the data record would also make little sense, since the JSON would otherwise be unusable, which is why I decided to complete the already solved machines again in the coming time and to document the necessary steps, e.g. to get root<br>

I ask for your indulgence, however, if the structuring is a bit unusual or if the steps are difficult to understand at first, since I first have to gain experience with the documentation and may need some time to improve the work.<br>

However, I will try to find a good way to constantly improve and provide good quality writeups.<br>

You can then find these in the [overview of the projects](https://antisectech.github.io/projects/). I hope you have a lot of fun reading it.
