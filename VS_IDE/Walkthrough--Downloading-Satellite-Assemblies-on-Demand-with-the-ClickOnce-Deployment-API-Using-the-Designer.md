---
title: "Walkthrough: Downloading Satellite Assemblies on Demand with the ClickOnce Deployment API Using the Designer"
ms.custom: na
ms.date: 10/03/2016
ms.devlang: 
  - VB
  - CSharp
  - C++
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - vs-ide-deployment
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 82b85a47-b223-4221-a17c-38a52c3fb6e2
caps.latest.revision: 10
manager: wpickett
translation.priority.ht: 
  - cs-cz
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - pl-pl
  - pt-br
  - ru-ru
  - tr-tr
  - zh-cn
  - zh-tw
---
# Walkthrough: Downloading Satellite Assemblies on Demand with the ClickOnce Deployment API Using the Designer
Windows Forms applications can be configured for multiple cultures through the use of satellite assemblies. A *satellite assembly* is an assembly that contains application resources for a culture other than the application's default culture.  
  
 As discussed in [Localizing ClickOnce Applications](../VS_IDE/Localizing-ClickOnce-Applications.md), you can include multiple satellite assemblies for multiple cultures within the same ClickOnce deployment. By default, ClickOnce will download all of the satellite assemblies in your deployment to the client machine, although a single client will probably require only one satellite assembly.  
  
 This walkthrough demonstrates how to mark your satellite assemblies as optional, and download only the assembly a client machine needs for its current culture settings.  
  
> [!NOTE]
>  For testing purposes, the following code examples programmatically set the culture to `ja-JP`. See the "Next Steps" section later in this topic for information on how to adjust this code for a production environment.  
  
### To mark satellite assemblies as optional  
  
1.  Build your project. This will generate satellite assemblies for all of the cultures you are localizing to.  
  
2.  Right-click on your project name in Solution Explorer, and click **Properties**.  
  
3.  Click the **Publish** tab, and then click **Application Files**.  
  
4.  Select the **Show all files** check box to display satellite assemblies. By default, all satellite assemblies will be included in your deployment and will be visible in this dialog box.  
  
     A satellite assembly will have a name in the form *isoCode*\ApplicationName.resources.dll, where *isoCode* is a language identifier in RFC 1766 format.  
  
5.  Click **New...** in the **Download Group** list for each language identifier. When prompted for a download group name, enter the language identifier. For example, for a Japanese satellite assembly, you would specify the download group name `ja-JP`.  
  
6.  Close the **Application Files** dialog box.  
  
### To download satellite assemblies on demand in C#  
  
1.  Open the Program.cs file. If you do not see this file in Solution Explorer, select your project, and on the **Project** menu, click **Show All Files**.  
  
2.  Use the following code to download the appropriate satellite assembly and start your application.  
  
     [!CODE [ClickOnce.SatelliteAssemblies#1](../CodeSnippet/VS_Snippets_Winforms/ClickOnce.SatelliteAssemblies#1)]  
  
### To download satellite assemblies on demand in Visual Basic  
  
1.  In the **Properties** window for the application, click the **Application** tab.  
  
2.  At the bottom of the tab page, click **View Application Events**.  
  
3.  Add the following imports to the beginning of the ApplicationEvents.VB file.  
  
     [!CODE [ClickOnce.SatelliteAssembliesVB#1](../CodeSnippet/VS_Snippets_Winforms/ClickOnce.SatelliteAssembliesVB#1)]  
  
4.  Add the following code to the `MyApplication` class.  
  
     [!CODE [ClickOnce.SatelliteAssembliesVB#2](../CodeSnippet/VS_Snippets_Winforms/ClickOnce.SatelliteAssembliesVB#2)]  
  
## Next Steps  
 In a production environment, you will likely need to remove the line in the code examples that sets <xref:System.Threading.Thread.CurrentUICulture?qualifyHint=False> to a specific value, because client machines will have the correct value set by default. When your application runs on a Japanese client machine, for example, <xref:System.Threading.Thread.CurrentUICulture?qualifyHint=False> will be `ja-JP` by default. Setting it programmatically is a good way to test your satellite assemblies before you deploy your application.  
  
## See Also  
 [Walkthrough: Downloading Satellite Assemblies on Demand with the ClickOnce Deployment API](../VS_IDE/Walkthrough--Downloading-Satellite-Assemblies-on-Demand-with-the-ClickOnce-Deployment-API.md)   
 [Localizing ClickOnce Applications](../VS_IDE/Localizing-ClickOnce-Applications.md)