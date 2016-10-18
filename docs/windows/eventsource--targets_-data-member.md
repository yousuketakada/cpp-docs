---
title: "EventSource::targets_ Data Member"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "event/Microsoft::WRL::EventSource::targets_"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "targets_ data member"
ms.assetid: 5d5cee05-3315-4514-bce2-19173c923c7d
caps.latest.revision: 4
ms.author: "mblome"
manager: "ghogen"
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
# EventSource::targets_ Data Member
An array of one or more event handlers.  
  
## Syntax  
  
```  
ComPtr<Details::EventTargetArray> targets_;  
```  
  
## Remarks  
 When the event that is represented by the current EventSource object occurs, the event handlers are called.  
  
## Requirements  
 **Header:** event.h  
  
 **Namespace:** Microsoft::WRL