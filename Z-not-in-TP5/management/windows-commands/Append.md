---
title: Append
ms.custom: na
ms.prod: windows-server-2012
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 9c3fea20-9502-40ad-a442-7a927aad88eb
---
# Append
Allows programs to open data files in specified directories as if they were in the current directory. If used without parameters, **append** displays the appended directory list.

For examples of how to use this command, see [Examples](#BKMK_examples).

## Syntax

```
append [[<Drive>:]<Path>[;...]] [/x[:on|:off]] [/path:[:on|:off] [/e] 
append ;
```

## Parameters

|Parameter|Description|
|-------------|---------------|
|\[<Drive>:\]<Path>|Specifies a drive and directory to append.|
|\/x:on|Applies appended directories to file searches and launching applications.|
|\/x:off|Applies appended directories only to requests to open files.<br /><br />**\/x:off** is the default setting.|
|\/path:on|Applies appended directories to file requests that already specify a path. **\/path:on** is the default setting.|
|\/path:off|Turns off the effect of **\/path:on**.|
|\/e|Stores a copy of the appended directory list in an environment variable named APPEND. **\/e** may be used only the first time you use **append** after starting your system.|
|;|Clears the appended directory list.|
|\/?|Displays help at the command prompt.|

## <a name="BKMK_examples"></a>Examples
To clear the appended directory list, type:

```
append ;
```

To store a copy of the appended directory to an environment variable named APPEND, type:

```
append /e
```

#### Additional references
[Command-Line Syntax Key](Command-Line-Syntax-Key.md)

