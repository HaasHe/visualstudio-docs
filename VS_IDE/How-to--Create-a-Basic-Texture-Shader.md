---
title: "How to: Create a Basic Texture Shader"
ms.custom: na
ms.date: 10/03/2016
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - vs-ide-general
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 5af113fb-6415-4be0-8b23-10fddb10e80a
caps.latest.revision: 23
manager: ghogen
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
# How to: Create a Basic Texture Shader
This document demonstrates how to use the Shader Designer and the Directed Graph Shader Language (DGSL) to create a single-texture shader. This shader sets the final color directly to the RGB and alpha values that are sampled from the texture.  
  
 This document demonstrates these activities:  
  
-   Removing nodes from a shader graph  
  
-   Adding nodes to a graph  
  
-   Setting shader parameters  
  
-   Setting parameter visibility  
  
-   Connecting nodes  
  
## Creating a basic texture shader  
 You can implement a basic, single-texture shader by writing the color and alpha values of a texture sample directly to the final output color.  
  
 Before you begin, make sure that the **Properties** window and the **Toolbox** are displayed.  
  
#### To create a basic texture shader  
  
1.  Create a DGSL shader to work with. For information about how to add a DGSL shader to your project, see the Getting Started section in [Shader Designer](../VS_IDE/Shader-Designer.md).  
  
2.  Delete the **Point Color** node. In **Select** mode, select the **Point Color** node, and then on the menu bar, choose **Edit**, **Delete**. This makes room for the node that's added in the next step.  
  
3.  Add a **Texture Sample** node to the graph. In the **Toolbox**, under **Texture**, select **Texture Sample** and move it to the design surface.  
  
4.  Add a **Texture Coordinate** node to the graph. In the **Toolbox**, under **Texture**, select **Texture Coordinate** and move it to the design surface.  
  
5.  Choose a texture to apply. In **Select** mode, select the **Texture Sample** node, and then in the **Properties** window, specify the texture that you want to use by using the **Filename** property.  
  
6.  Make the texture publicly accessible. Select the **Texture Sample** node, and then in the **Properties** window, set the **Access** property to **Public**. Now you can set the texture from another tool, such as the **Model Editor**.  
  
7.  Connect the texture coordinates to the texture sample. In **Select** mode, move the **Output** terminal of the **Texture Coordinate** node to the **UV** terminal of the **Texture Sample** node. This connection samples the texture at the specified coordinates.  
  
8.  Connect the texture sample to the final color. Move the **RGB** terminal of the **Texture Sample** node to the **RGB** terminal of the **Final Color** node, and then move the **Alpha** terminal of the **Texture Sample** node to the **Alpha** terminal of the **Final Color** node.  
  
 The following illustration shows the completed shader graph and a preview of the shader applied to a cube.  
  
> [!NOTE]
>  In this illustration, a plane is used as the preview shape, and a texture has been specified to better demonstrate the effect of the shader.  
  
 ![Shader graph and a preview of its effect](../VS_IDE/media/Digit-Texture-Effect.png "Digit-Texture-Effect")  
  
 Certain shapes might provide better previews for some shaders. For more information about how to preview shaders in the Shader Designer, see [Shader Designer](../VS_IDE/Shader-Designer.md)  
  
## See Also  
 [How to: Apply a Shader to a 3-D Model](../VS_IDE/How-to--Apply-a-Shader-to-a-3-D-Model.md)   
 [Image Editor](../VS_IDE/Image-Editor.md)   
 [Shader Designer](../VS_IDE/Shader-Designer.md)   
 [Shader Designer Nodes](../VS_IDE/Shader-Designer-Nodes.md)