---
title: "Useful PowerShell commands 🖥️"
date: 2025-02-01 09:00:00+0100h
categories: [tools]
tags: [tools, powershell]
---

## Show result of the command on ui and write to file 📝
```powershell
<command> | Tee-Object -FilePath <file_path_to_store_output>
```

## Show last n rows of some file 📄
```powershell
Get-Content -Path <file_path> -Tail n
```

## Copy result of the command to the clipboard 📋
```powershell
<command> | Set-Clipboard
```
