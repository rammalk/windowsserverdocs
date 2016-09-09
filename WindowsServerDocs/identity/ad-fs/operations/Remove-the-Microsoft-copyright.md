---
title: Remove the Microsoft copyright
description:
author: billmath
manager: femila
ms.date: 08/31/2016
ms.topic: article
ms.prod: windows-server-threshold
ms.service: active-directory
ms.technology: active-directory-federation-services
---
# Remove the Microsoft copyright 

>Applies To: Windows Server 2016, Windows Server 2012 R2
 
By default, the AD FS pages contain the Microsoft copyright. To remove this copyright from your customized pages, you can use the following procedure. 

![](media/AD-FS-user-sign-in-customization/ADFS_Blue_Custom1.png) 
  
## To remove the Microsoft copyright  
  
1.  Create a custom theme that is based on the default.  
  

    `New-AdfsWebTheme –Name custom –SourceName default ` 
 
  
2.  Export the theme by specifying the output folder.  

	`Export-AdfsWebTheme -Name custom -DirectoryPath C:\customWebTheme ` 

  
3.  Locate the Style.css file that is located in the output folder. By using the previous example, the path would be C:\\CustomWebTheme\\Css\\Style.css.  
  
4.  Open the Style.css file with an editor, such as Notepad.  
  
5.  Locate the `#copyright` portion, and then change it to the following:  
  `#copyright {color:#696969; display:none;} ` 
 
6.  Create a custom theme that is based on the new Style.css file.  
  
    `Set-AdfsWebTheme -TargetName custom -StyleSheet @{locale="";path="C:\customWebTheme\css\style.css"}  `

7.  Activate the new theme.  
  

    `Set-AdfsWebConfig -ActiveThemeName custom ` 


Now, you should no longer see the copyright at the bottom of the sign-in page.

![](media/AD-FS-user-sign-in-customization/ADFS_Blue_Custom1a.png) 

## Additional references 
[AD FS User Sign-in Customization](AD-FS-user-sign-in-customization.md) 