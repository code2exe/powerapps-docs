---
title: "Client API grid context in model-driven apps| MicrosoftDocs"
description: "Describes the client api grid context"
author: fikaradz
ms.author: fikaradz
ms.date: 04/18/2024
ms.reviewer: jdaly
ms.topic: "conceptual"
applies_to: 
  - "Dynamics 365 (online)"
ms.subservice: mda-developer
search.audienceType: 
  - developer
contributors: 
  - JimDaly
  - caburk
  - fikaradz
---
# Client API grid context

Grids present data in a tabular format. Grids can span the entire form or can be one of the items on a form; the latter are called **subgrids**.

The Client API grid context object provides reference to a subgrid on a form against which the current code is executed. 

> [!NOTE]
> Getting the context of a grid (spanning the entire form) is only supported in ribbon commands. More information: [Form and grid context in ribbon actions](../pass-data-page-parameter-ribbon-actions.md#form-and-grid-context-in-ribbon-actions)

Use the [formContext](clientapi-form-context.md) object to get an instance of the form where the code is executed, and then retrieve the subgrid control on the form. For example, when you know the name of a subgrid control (say **Contacts** subgrid in the default account form), you can access it using the following code:

```JavaScript
function doSomething(executionContext) {
   var formContext = executionContext.getFormContext(); // get the form Context
   var gridContext = formContext.getControl("Contacts"); // get the grid context

   // Perform operations on the subgrid
}
```

> [!NOTE]
> When using `gridContext`, calls to `getControl()` are not supported.


## Related articles

[Client API form context](clientapi-form-context.md)   
[Client API execution context](clientapi-execution-context.md)   
[Understand the Client API object model](understand-clientapi-object-model.md)  
[Grids and subgrids](reference/grids.md)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
