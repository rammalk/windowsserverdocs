---
title: format
description: "Windows Commands topic for **** - "
ms.custom: na
ms.prod: windows-server-threshold
ms.reviewer: na
ms.suite: na
ms.technology: manage-windows-commands
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 56863741-c5f3-4681-8667-2d566c8ddf23
author: coreyp-at-msft
ms.author: coreyp
manager: dongill
ms.date: 10/12/2016
---
# format

>Applies To: Windows Server 2016, Windows Server 2012 R2, Windows Server 2012

formats the partition or volume with focus for use with Windows.  
  
  
  
## Syntax  
  
```  
format [{fs=<ntfs|fat|fat32>] [revision=<x.xx>] | recommended}] [label=<label>] [unit=<n>] [quick] [compress] [override] [duplicate] [nowait] [noerr]  
```  
  
## Parameters  
  
|Parameter|Description|  
|-------|--------|  
|fs\=<ntfs&#124;fat&#124;fat32&#124;UDF>|Specifies the type of file system. If no file system is specified, the default file system is used. To view the default file system, run the **filesystems** command in DiskPart.|  
|revision\=<x.xx>|Specifies the file system revision \(if applicable\).|  
|recommended|if a recommended file system exists, DiskPart will use that file system and revision instead of the default file system and revision. To view the recommended file system \(if one exists\), run the **filesystems** command in DiskPart.|  
|label\=<label>|Specifies the volume label.|  
|unit\=<n>|Overrides the default allocation unit size. Default settings are strongly recommended for general use. To view the default allocation unit size for each file system that is supported by the volume, run the **filesystems** command in DiskPart. Note that NTFS compression is not supported for allocation unit sizes above 4096.|  
|quick|Performs a quick format.|  
|compress|This parameter only applies to volumes that will be formatted with the NTFS file system. When you use this command, files created on the new volume will be compressed by default.|  
|override|forces the volume to dismount first if necessary. If the volume is forcefully dismounted, some open handles \(files in use by an application\) to that volume can become invalid.|  
|duplicate|This parameter applies only to the universal disk format \(UDF\), revision 2.50 and above, for use with cd\-RW media and hard drives. When this parameter is used, DiskPart duplicates the file system metadata on a second set of sectors on the disk. The duplicate metadata will be used by applications \(for example repair or recovery applications\) if the primary metadata sectors become corrupt.|  
|nowait|Specifies to return the format immediately while the operation is still in progress. If this parameter is not specified, DiskPart will print out formatting progress in percentage.|  
|noerr|for scripting only. When an error is encountered, DiskPart continues to process commands as if the error did not occur. Without this parameter, an error causes DiskPart to exit with an error code.|  
  
## remarks  
  
-   A partition or volume must be selected for this operation to succeed. Use the **select partition** or the **select volume** command to select a partition or volume and shift the focus to it.  
  
## <a name="BKMK_examples"></a>Examples  
To perform a quick format of a partition or volume with the NTFS file system, assign the "Main volume" label to it, and specify that files added to the new volume be compressed by default, type:  
  
```  
format fs=ntfs label="Main volume" quick compress  
```  
  
To format the selected partition or volume that uses the recommended file system and force the volume to dismount if necessary, type:  
  
```  
format recommended override  
```  
  
#### additional references  
[Command-Line Syntax Key](command-line-syntax-key.md)  
  

  
