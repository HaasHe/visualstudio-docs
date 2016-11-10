---
title: "Name of type parameter &#39;&lt;typeparametername1&gt;&#39; does not match &#39;&lt;typeparametername2&gt;&#39;, the corresponding type parameter defined on the partial method declaration &#39;&lt;methodname&gt;&#39;"
ms.custom: na
ms.date: 10/01/2016
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-csharp
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 27c81cc1-325e-4e86-9d00-34f81e928076
caps.latest.revision: 5
manager: douge
translation.priority.ht: 
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - ru-ru
  - zh-cn
  - zh-tw
translation.priority.mt: 
  - cs-cz
  - pl-pl
  - pt-br
  - tr-tr
---
# Name of type parameter &#39;&lt;typeparametername1&gt;&#39; does not match &#39;&lt;typeparametername2&gt;&#39;, the corresponding type parameter defined on the partial method declaration &#39;&lt;methodname&gt;&#39;
In a partial method that includes one or more type parameters, the names of the type parameters must be the same in the declaration of the method and in the implementation of the method.  
  
 For example, the following declaration and implementation cause this error.  
  
```vb#  
' Definition of the partial method signature with type parameter T.  
Partial Private Sub OnNameChanged(Of T)()  
End Sub  
```  
  
```vb#  
'' Implementation of the partial method with type parameter N.  
'Private Sub OnNameChanged(Of N)()  
'    Console.WriteLine("Name was changed to " & Me.Name)  
'End Sub  
```  
  
 **Error ID:** BC31443  
  
### To correct this error  
  
-   Examine the type parameters to determine where they do not match. Change the names as necessary to make them the same.  
  
## See Also  
 [Partial Methods](../Topic/Partial%20Methods%20\(Visual%20Basic\).md)   
 [Generic Procedures in Visual Basic](../Topic/Generic%20Procedures%20in%20Visual%20Basic.md)