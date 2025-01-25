---
title: "Vi Mode in PowerShell 🖥️"
date: 2025-01-25 14:00:00+0100h
categories: [tools]
tags: [tools, powershell, vi]
---

## Motivation 🎯
On a daily basis, I use vim motions in many tools like VSCode, Cursor, JetBrains, etc.
Recently, I discovered a way to use vim motions in PowerShell as well.

## Installation ⚙️
First, you need to install the `PsReadline` module:
```powershell
Install-Module PsReadline -Scope CurrentUser
```
After installation, you can enable vim motions by executing:
```powershell
Set-PSReadlineOption -EditMode vi
```
To avoid running this command every time, you can add it to your profile file.
The profile file is located at the path stored in the `$PROFILE` variable.
You can edit it using the command `notepad $PROFILE` and add `Set-PSReadlineOption -EditMode vi` to the bottom of the file.

## Usage ⌨️
You can now use vim motions while writing commands in PowerShell.
