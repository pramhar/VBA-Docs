---
title: Printer.ColumnSpacing property (Access)
keywords: vbaac10.chm12874
f1_keywords:
- vbaac10.chm12874
ms.prod: access
api_name:
- Access.Printer.ColumnSpacing
ms.assetid: 058fbbf6-5c39-063a-e0a6-6b1942df0a4e
ms.date: 03/23/2019
ms.localizationpriority: medium
---


# Printer.ColumnSpacing property (Access)

Returns or sets a **Long** representing the vertical space between detail sections in [twips](../language/glossary/vbe-glossary.md#twip). Read/write.


## Syntax

_expression_.**ColumnSpacing**

_expression_ A variable that represents a **[Printer](Access.Printer.md)** object.


## Example

The following example sets a variety of printer settings for the form specified in the _strFormname_ argument of the procedure.

```vb
Sub SetPrinter(strFormname As String) 
 
 DoCmd.OpenForm FormName:=strFormname, view:=acDesign, _ 
 datamode:=acFormEdit, windowmode:=acHidden 
 
 With Forms(form1).Printer 
 
 .TopMargin = 1440 
 .BottomMargin = 1440 
 .LeftMargin = 1440 
 .RightMargin = 1440 
 
  .ColumnSpacing = 360 
 .RowSpacing = 360 
 
 .ColorMode = acPRCMColor 
 .DataOnly = False 
 .DefaultSize = False 
 .ItemSizeHeight = 2880 
 .ItemSizeWidth = 2880 
 .ItemLayout = acPRVerticalColumnLayout 
 .ItemsAcross = 6 
 
 .Copies = 1 
 .Orientation = acPRORLandscape 
 .Duplex = acPRDPVertical 
 .PaperBin = acPRBNAuto 
 .PaperSize = acPRPSLetter 
 .PrintQuality = acPRPQMedium 
 
 End With 
 
 DoCmd.Close objecttype:=acForm, objectname:=strFormname, _ 
 Save:=acSaveYes 
 
 
End Sub
```




[!include[Support and feedback](~/includes/feedback-boilerplate.md)]