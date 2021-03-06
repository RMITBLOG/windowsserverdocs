---
title: wbadmin get versions
description: Reference article for wbadmin get versions, which lists details about the available backups that are stored on the local computer or another computer.
ms.topic: reference
ms.assetid: b986acc4-d083-4d32-9434-862314ed5e97
ms.author: lizross
author: eross-msft
manager: mtillman
ms.date: 10/16/2017
---

# wbadmin get versions



Lists details about the available backups that are stored on the local computer or another computer. When this subcommand is used without parameters, it lists all backups of the local computer, even if those backups are not available. The details provided for a backup include the backup time, the backup storage location, the version identifier (needed for the **wbadmin get items** subcommand and to perform recoveries), and the type of recoveries you can perform.

To get details about available backups using this subcommand, you must be a member of the **Backup Operators** group or the **Administrators** group, or you must have been delegated the appropriate permissions. In addition, you must run **wbadmin** from an elevated command prompt. (To open an elevated command prompt **Command Prompt** and then click **Run as administrator**.)

## Syntax

```
wbadmin get versions
[-backupTarget:{<BackupTargetLocation> | <NetworkSharePath>}]
[-machine:BackupMachineName]
```

### Parameters

|Parameter|Description|
|---------|-----------|
|-backupTarget|Specifies the storage location that contains the backups that you want the details for. Use for listing backups stored at that target location. Backup target locations can be locally attached disk drives, volumes, remote shared folders, removable media such as DVD drives or other optical media. If **wbadmin get versions** is run on the same computer where the backup was created, this parameter is not needed. However, this parameter is required to get information about a backup created from another computer.|
|-machine|Specifies the computer that you want backup details for. Use when backups of multiple computers are stored in the same location. Should be used when **-backupTarget** is specified.|

## Remarks

To list items available for recovery from a specific backup, use **wbadmin get items**.

## Examples

To see a list of available backups that are stored on volume h, type:
```
wbadmin get versions -backupTarget:h:
```
To see a list of available backups that are stored in the remote shared folder \\\\servername\share for the computer server01, type:
```
wbadmin get versions -backupTarget:\\servername\share -machine:server01
```

## Additional References

- [Command-Line Syntax Key](command-line-syntax-key.md)
-   [Wbadmin](wbadmin.md)
-   [Get-WBBackupTarget](/powershell/module/windowserverbackup/?view=winserver2012r2-ps) cmdlet
