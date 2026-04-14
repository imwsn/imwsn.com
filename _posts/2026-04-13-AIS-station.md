---
title: AIS APRS Receiver and LoRa APRS iGate
date:2026-04-13
category: notes
---

最近用RTL-SDR v3 安装了AIS receiver,监听哈德逊河上面的船只信息,并且上传到aprs.fi上

```
AIS-catcher -H http://aprs.fi/jsonais/post/{AIS password} ID {CALL SIGN} PROTOCOL aprs INTERVAL 30 LAT {LAT_VALUE} LON  {LON_VALUE}
```

然后把这个作为系统服务,就可以监听船只信息上传到aprs.fi上,上传之后就会在我的位置显示一个小绿塔.

我用heltec v4安装了 [LoRa_APRS_iGate](https://github.com/richonguzman/LoRa_APRS_iGate) 之后,接了一个3dB 915MHz天线,标上坐标之后就成了一个LoRa APRS iGate上传到aprs.fi了
 
现在我当前的位置有个LoRa APRS iGate和一个AIS receiver
