---
title: "Amazon Linux 2ã®Timezoneå¤æ´"
emoji: "ð"
type: "tech" # tech: æè¡è¨äº / idea: ã¢ã¤ãã¢
topics: ["AWS", "EC2", "Timezone", "Linux", "JST", "UTC"]
publication_name: "minedia"
published: true
---

# æ¦è¦

- Amazon Linux 2ã§Timezoneãå¤æ´ããæ¹æ³ãè¨è¼ãã¦ããã¾ãã

# è¨­å®

ç¾å¨ãUTCã§è¡¨ç¤ºããã¦ããããç¢ºèªãã¾ãã

```
[root@ip-10-0-0-141 ssm-user]# date
Fri Jul 29 15:18:56 UTC 2021
```

timedatedctlã³ãã³ãçµç±ã§å¤æ´ãã¾ãã

```
[root@ip-10-0-0-141 ssm-user]# timedatectl set-timezone Asia/Tokyo
```

crondã«å¯¾ãã¦ãå¤æ´ãåæ ããããã«åèµ·åãã¦ããã¾ãã

```
[root@ip-10-0-0-141 ssm-user]# systemctl restart crond.service
```

JSTã§è¡¨ç¤ºãããããç¢ºèªãã¾ãã

```
[root@ip-10-0-0-141 ssm-user]# date
Fri Jul 30 00:20:56 JST 2021
```


# è£è¶³

`/etc/sysconfig/clock` ãã¡ã¤ã«ã¯å­å¨ãã¦ããªãããã§ãã

```
[root@ip-10-0-0-141 ssm-user]# cat /etc/sysconfig/clock
cat: /etc/sysconfig/clock: No such file or directory
```
