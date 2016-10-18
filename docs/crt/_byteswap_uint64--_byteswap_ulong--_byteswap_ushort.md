---
title: "_byteswap_uint64, _byteswap_ulong, _byteswap_ushort"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_byteswap_uint64"
  - "_byteswap_ulong"
  - "_byteswap_ushort"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-utility-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "byteswap_ulong"
  - "_byteswap_ulong"
  - "byteswap_uint64"
  - "_byteswap_ushort"
  - "_byteswap_uint64"
  - "byteswap_ushort"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_byteswap_uint64 function"
  - "byteswap_uint64 function"
  - "swapping bytes"
  - "byte swapping"
  - "byteswap_ushort function"
  - "_byteswap_ushort function"
  - "bytes, swapping"
  - "byteswap_ulong function"
  - "_byteswap_ulong function"
ms.assetid: 83bda211-f02f-4cf0-8a78-d6de1f175970
caps.latest.revision: 12
ms.author: "corob"
manager: "ghogen"
translation.priority.ht: 
  - "cs-cz"
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "pl-pl"
  - "pt-br"
  - "ru-ru"
  - "tr-tr"
  - "zh-cn"
  - "zh-tw"
---
# _byteswap_uint64, _byteswap_ulong, _byteswap_ushort
Reverses the order of bytes in an integer.  
  
## Syntax  
  
```  
unsigned short _byteswap_ushort (  
   unsigned short val  
);  
unsigned long _byteswap_ulong (  
   unsigned long val  
);  
unsigned __int64 _byteswap_uint64 (  
   unsigned __int64 val  
);  
```  
  
#### Parameters  
 `val`  
 The integer to reverse byte order.  
  
## Requirements  
  
|Routine|Required header|  
|-------------|---------------------|  
|`_byteswap_ushort`|\<stdlib.h>|  
|`_byteswap_ulong`|\<stdlib.h>|  
|`_byteswap_uint64`|\<stdlib.h>|  
  
 For more compatibility information, see [Compatibility](../crt/compatibility.md) in the Introduction.  
  
## Example  
  
```  
// crt_byteswap.c  
#include <stdlib.h>  
  
int main()  
{  
   unsigned __int64 u64 = 0x0102030405060708;  
   unsigned long ul = 0x01020304;  
  
   printf("byteswap of %I64x = %I64x\n", u64, _byteswap_uint64(u64));  
   printf("byteswap of %Ix = %Ix", ul, _byteswap_ulong(ul));  
}  
```  
  
 **byteswap of 102030405060708 = 807060504030201**  
**byteswap of 1020304 = 4030201**   
## See Also  
 [Run-Time Routines by Category](../crt/run-time-routines-by-category.md)