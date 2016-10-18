---
title: "Conversion from &#39;Double&#39; to &#39;Date&#39; requires calling the &#39;Date.FromOADate&#39;"
ms.custom: na
ms.date: "10/13/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vbc30533"
  - "bc30533"
helpviewer_keywords: 
  - "BC30533"
ms.assetid: afcfd115-4614-4b0b-ad09-76af8dba2ed5
caps.latest.revision: 8
ms.author: "billchi"
manager: "douge"
translation.priority.ht: 
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "ru-ru"
  - "zh-cn"
  - "zh-tw"
translation.priority.mt: 
  - "cs-cz"
  - "pl-pl"
  - "pt-br"
  - "tr-tr"
---
# Conversion from &#39;Double&#39; to &#39;Date&#39; requires calling the &#39;Date.FromOADate&#39;
You have attempted to cast a `Date` value to a `Double` value, which cannot be done without using the \<xref:System.DateTime.FromOADate*?displayProperty=fullName> method.  
  
 **Error ID:** BC30533  
  
### To correct this error  
  
-   Use the \<xref:System.DateTime.FromOADate*> method to convert the value.  
  
## See Also  
 [Type Conversions in Visual Basic](../Topic/Type%20Conversions%20in%20Visual%20Basic.md)