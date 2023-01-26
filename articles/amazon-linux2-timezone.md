---
title: "Amazon Linux 2のTimezone変更"
emoji: "🕙"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["AWS", "EC2", "Timezone", "Linux", "JST", "UTC"]
publication_name: "minedia"
published: true
---

# 概要

- Amazon Linux 2でTimezoneを変更する方法を記載しておきます。

# 設定

現在がUTCで表示されているかを確認します。

```
[root@ip-10-0-0-141 ssm-user]# date
Fri Jul 29 15:18:56 UTC 2021
```

timedatedctlコマンド経由で変更します。

```
[root@ip-10-0-0-141 ssm-user]# timedatectl set-timezone Asia/Tokyo
```

crondに対しても変更を反映するために再起動しておきます。

```
[root@ip-10-0-0-141 ssm-user]# systemctl restart crond.service
```

JSTで表示されるかを確認します。

```
[root@ip-10-0-0-141 ssm-user]# date
Fri Jul 30 00:20:56 JST 2021
```


# 補足

`/etc/sysconfig/clock` ファイルは存在していないようです。

```
[root@ip-10-0-0-141 ssm-user]# cat /etc/sysconfig/clock
cat: /etc/sysconfig/clock: No such file or directory
```
