---
title: Uninstalling
layout: default
nav_order: 3
---

# Uninstallation

## MacOS

Navigate to the `Applications` folder in Finder and delete Portable-CELLxGENE.

## Windows

1. Open the command prompt (Windows key + "R", then type `cmd` and hit enter).
2. Copy the following into the command prompt and hit enter.

```batch
rmdir /q /s "%LOCALAPPDATA%\Portable-CELLxGENE"
del "%HOMEPATH%\Desktop\Portable-CELLxGENE.lnk"
del "%APPDATA%\Microsoft\Windows\Start Menu\Programs\Portable-CELLxGENE.lnk"
```
