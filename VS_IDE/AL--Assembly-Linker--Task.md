---
title: "AL (Assembly Linker) Task"
ms.custom: na
ms.date: 10/10/2016
ms.devlang: 
  - VB
  - CSharp
  - C++
  - jsharp
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - vs-ide-sdk
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 2ddefbf2-5662-4d55-99a6-ac383bf44560
caps.latest.revision: 22
manager: ghogen
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
# AL (Assembly Linker) Task
The AL task wraps AL.exe, a tool that is distributed with the Windows Software Development Kit (SDK). This Assembly Linker tool is used to create an assembly with a manifest from one or more files that are either modules or resource files. Compilers and development environments might already provide these capabilities, so it is often not necessary to use this task directly. The Assembly Linker is most useful to developers needing to create a single assembly from multiple component files, such as those that might be produced from mixed-language development. This task does not combine the modules into a single assembly file; the individual modules must still be distributed and available in order for the resulting assembly to load correctly. For more information on AL.exe, see [Al.exe (Assembly Linker)](../Topic/Al.exe%20\(Assembly%20Linker\).md).  
  
## Parameters  
 The following table describes the parameters of the `AL` task.  
  
|Parameter|Description|  
|---------------|-----------------|  
|`AlgorithmID`|Optional `String` parameter.<br /><br /> Specifies an algorithm to hash all files in a multifile assembly except the file that contains the assembly manifest. For more information, see the documentation for the `/algid` option in [Al.exe (Assembly Linker)](../Topic/Al.exe%20\(Assembly%20Linker\).md).|  
|`BaseAddress`|Optional `String` parameter.<br /><br /> Specifies the address at which a DLL will be loaded on the user’s computer at run time. Applications load faster if you specify the base address of the DLLs, rather than letting the operating system relocate the DLLs in the process space. This parameter corresponds to the /base[address] option in [Al.exe (Assembly Linker)](../Topic/Al.exe%20\(Assembly%20Linker\).md).|  
|`CompanyName`|Optional `String` parameter.<br /><br /> Specifies a string for the `Company` field in the assembly. For more information, see the documentation for the `/comp[any]` option in [Al.exe (Assembly Linker)](../Topic/Al.exe%20\(Assembly%20Linker\).md).|  
|`Configuration`|Optional `String` parameter.<br /><br /> Specifies a string for the `Configuration` field in the assembly. For more information, see the documentation for the `/config[uration]` option in [Al.exe (Assembly Linker)](../Topic/Al.exe%20\(Assembly%20Linker\).md).|  
|`Copyright`|Optional `String` parameter.<br /><br /> Specifies a string for the `Copyright` field in the assembly. For more information, see the documentation for the `/copy[right]` option in [Al.exe (Assembly Linker)](../Topic/Al.exe%20\(Assembly%20Linker\).md).|  
|`Culture`|Optional `String` parameter.<br /><br /> Specifies the culture string to associate with the assembly. For more information, see the documentation for the `/c[ulture]` option in [Al.exe (Assembly Linker)](../Topic/Al.exe%20\(Assembly%20Linker\).md).|  
|`DelaySign`|Optional `Boolean` parameter.<br /><br /> `true` to place only the public key in the assembly; `false` to fully sign the assembly. For more information, see the documentation for the `/delay[sign]` option in [Al.exe (Assembly Linker)](../Topic/Al.exe%20\(Assembly%20Linker\).md).|  
|`Description`|Optional `String` parameter.<br /><br /> Specifies a string for the `Description` field in the assembly. For more information, see the documentation for the `/descr[iption]` option in [Al.exe (Assembly Linker)](../Topic/Al.exe%20\(Assembly%20Linker\).md).|  
|`EmbedResources`|Optional <xref:Microsoft.Build.Framework.ITaskItem?qualifyHint=False>`[]` parameter.<br /><br /> Embeds the specified resources in the image that contains the assembly manifest. This task copies the contents of the resource file into the image. The items passed in to this parameter may have optional metadata attached to them called `LogicalName` and `Access`. The `LogicalName` metadata is used to specify the internal identifier for the resource.  The `Access` metadata can be set to `private` in order to make the resource not visible to other assemblies. For more information, see the documentation for the `/embed[resource]` option in [Al.exe (Assembly Linker)](../Topic/Al.exe%20\(Assembly%20Linker\).md).|  
|`EvidenceFile`|Optional `String` parameter.<br /><br /> Embeds the specified file in the assembly with the resource name of `Security.Evidence`.<br /><br /> You cannot use `Security.Evidence` for regular resources. This parameter corresponds to the `/e[vidence]` option in [Al.exe (Assembly Linker)](../Topic/Al.exe%20\(Assembly%20Linker\).md).|  
|`ExitCode`|Optional `Int32` output read-only parameter.<br /><br /> Specifies the exit code provided by the executed command.|  
|`FileVersion`|Optional `String` parameter.<br /><br /> Specifies a string for the `File Version` field in the assembly. For more information, see the documentation for the `/fileversion` option in [Al.exe (Assembly Linker)](../Topic/Al.exe%20\(Assembly%20Linker\).md).|  
|`Flags`|Optional `String` parameter.<br /><br /> Specifies a value for the `Flags` field in the assembly. For more information, see the documentation for the `/flags` option in [Al.exe (Assembly Linker)](../Topic/Al.exe%20\(Assembly%20Linker\).md).|  
|`GenerateFullPaths`|Optional `Boolean` parameter.<br /><br /> Causes the task to use the absolute path for any files that are reported in an error message. This parameter corresponds to the `/fullpaths` option in [Al.exe (Assembly Linker)](../Topic/Al.exe%20\(Assembly%20Linker\).md).|  
|`KeyContainer`|Optional `String` parameter.<br /><br /> Specifies a container that holds a key pair. This will sign the assembly (give it a strong name) by inserting a public key into the assembly manifest. The task will then sign the final assembly with the private key. For more information, see the documentation for the `/keyn[ame]` option in [Al.exe (Assembly Linker)](../Topic/Al.exe%20\(Assembly%20Linker\).md).|  
|`KeyFile`|Optional `String` parameter.<br /><br /> Specifies a file that contains a key pair or just a public key to sign an assembly. The compiler inserts the public key in the assembly manifest and then signs the final assembly with the private key. For more information, see the documentation for the `/keyf[ile]` option in [Al.exe (Assembly Linker)](../Topic/Al.exe%20\(Assembly%20Linker\).md).|  
|`LinkResources`|Optional <xref:Microsoft.Build.Framework.ITaskItem?qualifyHint=False>`[]` parameter.<br /><br /> Links the specified resource files to an assembly. The resource becomes part of the assembly, but the file is not copied. The items passed in to this parameter may have optional metadata attached to them called `LogicalName`, `Target`, and `Access`. The `LogicalName` metadata is used to specify the internal identifier for the resource. The `Target` metadata can specify the path and filename to which the task copies the file, after which it compiles this new file into the assembly. The `Access` metadata can be set to `private` in order to make the resource not visible to other assemblies. For more information, see the documentation for the `/link[resource]` option in [Al.exe (Assembly Linker)](../Topic/Al.exe%20\(Assembly%20Linker\).md).|  
|`MainEntryPoint`|Optional `String` parameter.<br /><br /> Specifies the fully qualified name (*class.method*) of the method to use as an entry point when converting a module to an executable file. This parameter corresponds to the `/main` option in [Al.exe (Assembly Linker)](../Topic/Al.exe%20\(Assembly%20Linker\).md).|  
|`OutputAssembly`|Required <xref:Microsoft.Build.Framework.ITaskItem?qualifyHint=False> output parameter.<br /><br /> Specifies the name of the file generated by this task. This parameter corresponds to the `/out` option in [Al.exe (Assembly Linker)](../Topic/Al.exe%20\(Assembly%20Linker\).md).|  
|`Platform`|Optional `String` parameter.<br /><br /> Limits which platform this code can run on; must be one of `x86`, `Itanium`, `x64`, or `anycpu`. The default is `anycpu`. This parameter corresponds to the `/platform` option in [Al.exe (Assembly Linker)](../Topic/Al.exe%20\(Assembly%20Linker\).md).|  
|`ProductName`|Optional `String` parameter.<br /><br /> Specifies a string for the `Product` field in the assembly. For more information, see the documentation for the `/prod[uct]` option in [Al.exe (Assembly Linker)](../Topic/Al.exe%20\(Assembly%20Linker\).md).|  
|`ProductVersion`|Optional `String` parameter.<br /><br /> Specifies a string for the `ProductVersion` field in the assembly. For more information, see the documentation for the `/productv[ersion]` option in [Al.exe (Assembly Linker)](../Topic/Al.exe%20\(Assembly%20Linker\).md).|  
|`ResponseFiles`|Optional `String[]` parameter.<br /><br /> Specifies the response files that contain additional options to pass through to the Assembly Linker.|  
|`SdkToolsPath`|Optional `String` parameter.<br /><br /> Specifies the path to the SDK tools, such as resgen.exe.|  
|`SourceModules`|Optional <xref:Microsoft.Build.Framework.ITaskItem?qualifyHint=False>`[]` parameter.<br /><br /> One or more modules to be compiled into an assembly. The modules will be listed in the manifest of the resulting assembly, and will still need to distributed and available in order for the assembly to load. The items passed into this parameter may have additional metadata called `Target`, which specifies the path and filename to which the task copies the file, after which it compiles this new file into the assembly. For more information, see the documentation for [Al.exe (Assembly Linker)](../Topic/Al.exe%20\(Assembly%20Linker\).md). This parameter corresponds to the list of modules passed into Al.exe without a specific switch.|  
|`TargetType`|Optional `String` parameter.<br /><br /> Specifies the file format of the output file: `library` (code library), `exe` (console application), or `win` (Windows-based application). The default is `library`. This parameter corresponds to the `/t[arget]` option in [Al.exe (Assembly Linker)](../Topic/Al.exe%20\(Assembly%20Linker\).md).|  
|`TemplateFile`|Optional `String` parameter.<br /><br /> Specifies the assembly from which to inherit all assembly metadata, except the culture field. The specified assembly must have a strong name.<br /><br /> An assembly that you create with the `TemplateFile` parameter will be a satellite assembly. This parameter corresponds to the `/template` option in [Al.exe (Assembly Linker)](../Topic/Al.exe%20\(Assembly%20Linker\).md).|  
|`Timeout`|Optional `Int32` parameter.<br /><br /> Specifies the amount of time, in milliseconds, after which the task executable is terminated. The default value is `Int.MaxValue`, indicating that there is no time out period.|  
|`Title`|Optional `String` parameter.<br /><br /> Specifies a string for the `Title` field in the assembly. For more information, see the documentation for the `/title` option in [Al.exe (Assembly Linker)](../Topic/Al.exe%20\(Assembly%20Linker\).md).|  
|`ToolPath`|Optional `String` parameter.<br /><br /> Specifies the location from where the task will load the underlying executable file (Al.exe). If this parameter is not specified, the task uses the SDK installation path corresponding to the version of the framework that is running MSBuild.|  
|`Trademark`|Optional `String` parameter.<br /><br /> Specifies a string for the `Trademark` field in the assembly. For more information, see the documentation for the `/trade[mark]` option in [Al.exe (Assembly Linker)](../Topic/Al.exe%20\(Assembly%20Linker\).md).|  
|`Version`|Optional `String` parameter.<br /><br /> Specifies the version information for this assembly. The format of the string is *major.minor.build.revision*. The default value is 0. For more information, see the documentation for the `/v[ersion]` option in [Al.exe (Assembly Linker)](../Topic/Al.exe%20\(Assembly%20Linker\).md).|  
|`Win32Icon`|Optional `String` parameter.<br /><br /> Inserts an .ico file in the assembly. The .ico file gives the output file the desired appearance in File Explorer. This parameter corresponds to the `/win32icon` option in [Al.exe (Assembly Linker)](../Topic/Al.exe%20\(Assembly%20Linker\).md).|  
|`Win32Resource`|Optional `String` parameter.<br /><br /> Inserts a Win32 resource (.res file) in the output file. For more information, see the documentation for the `/win32res` option in [Al.exe (Assembly Linker)](../Topic/Al.exe%20\(Assembly%20Linker\).md).|  
  
## Remarks  
 In addition to the parameters listed above, this task inherits parameters from the <xref:Microsoft.Build.Tasks.ToolTaskExtension?qualifyHint=False> class, which itself inherits from the <xref:Microsoft.Build.Utilities.ToolTask?qualifyHint=False> class. For a list of these additional parameters and their descriptions, see [ToolTaskExtension Base Class](../VS_IDE/ToolTaskExtension-Base-Class.md).  
  
## Example  
 The following example creates an assembly with the specified options.  
  
```  
<AL  
    EmbedResources="@(EmbeddedResource)"  
    Culture="%(EmbeddedResource.Culture)"  
    TemplateFile="@(IntermediateAssembly)"  
    KeyContainer="$(KeyContainerName)"  
    KeyFile="$(KeyOriginatorFile)"  
    DelaySign="$(DelaySign)"  
  
    OutputAssembly=  
       "%(EmbeddedResource.Culture)\$(TargetName).resources.dll">  
  
    <Output TaskParameter="OutputAssembly"  
        ItemName="SatelliteAssemblies"/>  
</AL>  
```  
  
## See Also  
 [Task Reference](../VS_IDE/MSBuild-Task-Reference.md)   
 [Tasks](../VS_IDE/MSBuild-Tasks.md)