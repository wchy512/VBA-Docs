---
title: OptionGroup.DefaultValue property (Access)
keywords: vbaac10.chm10823
f1_keywords:
- vbaac10.chm10823
ms.prod: access
api_name:
- Access.OptionGroup.DefaultValue
ms.assetid: cb19cb7b-033c-9e4d-6683-5296c306f47f
ms.date: 02/21/2019
ms.localizationpriority: medium
---


# OptionGroup.DefaultValue property (Access)

Specifies a value that is automatically entered in a field when a new record is created. For example, in an **Addresses** table, you can set the default value for the **City** field to New York. When users add a record to the table, they can either accept this value or enter the name of a different city. Read/write **String**.


## Syntax

_expression_.**DefaultValue**

_expression_ A variable that represents an **[OptionGroup](Access.OptionGroup.md)** object.


## Remarks

The **DefaultValue** property applies to all table fields except those fields with the data type of AutoNumber or OLE Object.

The **DefaultValue** property specifies text or an expression that's automatically entered in a control or field when a new record is created. For example, if you set the **DefaultValue** property for a text box control to `=Now()`, the control displays the current date and time. The maximum length for a **DefaultValue** property setting is 255 characters.

The **DefaultValue** property doesn't apply to check box, option button, or toggle button controls when they are in an option group. However, it does apply to the option group itself.

In Visual Basic, use a string expression to set the value of this property. For example, the following code sets the **DefaultValue** property for a text box control named **PaymentMethod** to "Cash."

```vb
Forms!frmInvoice!PaymentMethod.DefaultValue = """Cash"""
```

> [!NOTE] 
> To set this property for a field by using Visual Basic, use the ADO **DefaultValue** property or the DAO **DefaultValue** property.

The **DefaultValue** property is applied only when you add a new record. If you change the **DefaultValue** property, the change isn't automatically applied to existing records.

If you set the **DefaultValue** property for a form control that's bound to a field that also has a **DefaultValue** property setting defined in the table, the control setting overrides the table setting.

If you create a control by dragging a field from the field list, the field's **DefaultValue** property setting, as defined in the table, is applied to the control on the form although the control's **DefaultValue** property setting will remain blank.

One control can provide the default value for another control. For example, if you set the **DefaultValue** property for a control to the following expression, the control's default value is set to the **DefaultValue** property setting for the **txtShipTo** control.

```vb
=Forms!frmInvoice!txtShipTo
```

If the controls are on the same form, the control that's the source of the default value must appear earlier in the tab order than the control containing the expression.




[!include[Support and feedback](~/includes/feedback-boilerplate.md)]

