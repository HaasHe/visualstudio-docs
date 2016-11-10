---
title: "Compiler Error CS0174"
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
  - "CS0174"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0174"
ms.assetid: c34c0fa4-d720-4dc5-b723-014203bab8f7
caps.latest.revision: 9
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
# Compiler Error CS0174
A base class is required for a 'base' reference  
  
 This error occurs only when the .NET Framework common language runtime compiles the source code for the `System.Object` class, which is the only class that has no base class.