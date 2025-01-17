---
title: GradientStops.Insert method (Office)
ms.prod: office
api_name:
- Office.GradientStops.Insert
ms.assetid: 98aec7ed-44f9-c9b4-7a1a-e5b9a1d26d95
ms.date: 01/16/2019
ms.localizationpriority: medium
---


# GradientStops.Insert method (Office)

Adds a stop to a gradient.


## Syntax

_expression_.**Insert** (_RGB_, _Position_, _Transparency_, _Index_)

_expression_ An expression that returns a **[GradientStops](Office.GradientStops.md)** object.


## Parameters

|Name|Required/Optional|Data type|Description|
|:-----|:-----|:-----|:-----|
| _RGB_|Required|**[MsoThemeColorSchemeIndex](office.msothemecolorschemeindex.md)**|Specifies the color at the gradient stop.|
| _Position_|Required|**Single**|Specifies the position of the stop within the gradient expressed as a percent.|
| _Transparency_|Optional|**Single**|Specifies the opacity of color at the gradient stop.|
| _Index_|Optional|**Long**|The index number of the stop.|

## Remarks

Gradients are a smooth transition from one color state to another. The endpoints of these sections are called stops.


## Example

The following example creates three color gradient stops in Microsoft PowerPoint.

```vb
Sub gradients() 
 Set myDocument = ActivePresentation.Slides(1) 
 Set GradientShapeFill = myDocument.Shapes.AddShape(msoShapeRectangle, 90, 90, 90, 80).Fill 
 With GradientShapeFill 
 .ForeColor.RGB = RGB(0, 128, 128) 
 .OneColorGradient msoGradientHorizontal, 1, 1 
 .GradientStops.Insert RGB(255, 0, 0), 0.25 
 .GradientStops.Insert RGB(0, 255, 0), 0.5 
 .GradientStops.Insert RGB(0, 0, 255), 0.75 
 End With 
End Sub 

```


## See also

- [GradientStops object members](overview/library-reference/gradientstops-members-office.md)

[!include[Support and feedback](~/includes/feedback-boilerplate.md)]