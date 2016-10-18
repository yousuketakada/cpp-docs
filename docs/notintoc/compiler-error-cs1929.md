---
title: "Compiler Error CS1929"
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
  - "CS1929"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1929"
ms.assetid: effdd5d4-e156-418b-9d45-4ca194ab4319
caps.latest.revision: 6
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
# Compiler Error CS1929
Instance argument: cannot convert from 'typeA' to 'typeB'.  
  
 This error is generated when you try to invoke an extension method from a class that it does not extend. In the example shown here, the extension method is defined for the derived class `A`, but not for the base class `B`.  
  
### To correct this error  
  
1.  Create a new extension method for the type where you have to invoke it, or else move the call into an object of the type that the existing method extends.  
  
## Example  
 The following code generates CS1928 and CS1929:  
  
```  
// cs1929.cs  
using System.Linq;  
    using System.Collections;  
  
    static class Ext  
    {  
        public static void ExtMethod(this A a)  
        {  
        }  
    }  
  
    class A : B  
    {  
    }  
  
    class B  
    {  
        static void Main()  
        {  
            B b = new B();  
            b.ExtMethod(); // CS1929  
        }  
    }  
```  
  
## See Also  
 [Extension Methods](../Topic/Extension%20Methods%20\(C%23%20Programming%20Guide\).md)