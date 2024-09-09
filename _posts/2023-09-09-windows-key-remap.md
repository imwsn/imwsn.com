---
title: Windows Key Remap
category: notes
date: 2024-09-09
---

I want to map "Left Win"(Meta) key to "Left Control" in windows. There are 2 solutions.

1. Update Registreray directly
   ```
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Keyboard Layout]
   "Scancode Map"=hex:00,00,00,00,00,00,00,00,02,00,00,00,1d,00,5b,e0,00,00,00,00
   ```

2. Use [SharpKeys](https://github.com/randyrants/sharpkeys/releases), update the keymap then reboot.


Reference from [StackOverflow](https://superuser.com/questions/1264164/how-to-map-windows-key-to-ctrl-key-on-windows-10)


