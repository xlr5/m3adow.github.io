---
layout: default
title: "Linux: Empty swap space"
categories:
- linux
---

*This is the translation of a [post]({% post_url 2013-02-22-linux-swap-leeren %}) I wrote four years ago. I needed an english version of it for a friend of mine.*

If you want to empty your swap space on Linux for whatever reason, so you can simply use these commands:

```bash
swapoff -a && swapon -a
```

This deactivates all swap storage first, leading to a drainage of the currently contained data. Afterwards the swap space is activated again.

If the swap space is heavily utilized, this can take a couple of minutes, so don't worry if nothing happens. To check the progress, you can use this command in another window:

```bash
free -s 3 |grep Swap
```

This command shows the current used swap and refreshes every three seconds. Of course, the used swap space should continously decrease and finally be zero.

If you only want to empty one swap partition, you can substitute the `-a` switch in the first command with the paritition you want to drain, e.g. `/dev/sda2`.

*([via](https://wiki.ubuntuusers.de/Swap))*
