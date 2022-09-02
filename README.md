<!-- default badges list -->
[![](https://img.shields.io/badge/Open_in_DevExpress_Support_Center-FF7200?style=flat-square&logo=DevExpress&logoColor=white)](https://supportcenter.devexpress.com/ticket/details/T1109273)
[![](https://img.shields.io/badge/📖_How_to_use_DevExpress_Examples-e9f6fc?style=flat-square)](https://docs.devexpress.com/GeneralInformation/403183)
<!-- default badges end -->
# Rich Edit for Blazor - How to implement custom saving

The [Rich Text Editor](https://docs.devexpress.com/Blazor/DevExpress.Blazor.RichEdit.DxRichEdit) allows you to customize its built-in UI. In this example, the Rich Text Editor displays the custom **Final Save** button in the **File** ribbon tab. When a user clicks this button, the control performs the following actions:

1. Updates [fields](https://docs.devexpress.com/Blazor/DevExpress.Blazor.RichEdit.Field#remarks) in an open document.
2. Clears the content of the first section's [header](https://docs.devexpress.com/Blazor/DevExpress.Blazor.RichEdit.Section#section-headers-and-footers).
3. Inserts an [image](https://docs.devexpress.com/Blazor/DevExpress.Blazor.RichEdit.Image#remarks) to the header.
4. [Saves](https://docs.devexpress.com/Blazor/DevExpress.Blazor.RichEdit.DxRichEdit.SaveDocumentAsync(System.Threading.CancellationToken)) the open document.

![Blazor Rich Edit implement custom saving](images/custom-saving.gif)

Handle the [CustomizeRibbon](https://docs.devexpress.com/Blazor/DevExpress.Blazor.RichEdit.DxRichEdit.CustomizeRibbon) event to customize the built-in ribbon. Use the event's parameter to access the **File** tab's **Common** item group. Call the group's [AddCustomButton](https://docs.devexpress.com/Blazor/DevExpress.Blazor.Office.BarItemCollection.AddCustomButton(System.Int32-System.String-System.Func-System.Threading.Tasks.Task-)) method to add the custom **Final Save** button to this group. The method's `click` parameter sets this button's [Click](https://docs.devexpress.com/Blazor/DevExpress.Blazor.Office.IBarButton.Click) event handler.

Bind the [DocumentContent](https://docs.devexpress.com/Blazor/DevExpress.Blazor.RichEdit.DxRichEdit.DocumentContent) property to a data field to enable save operations. Use the [Modified](https://docs.devexpress.com/Blazor/DevExpress.Blazor.RichEdit.DxRichEdit.Modified) property to check whether an open document has unsaved changes and depending on this [enable/disable](https://docs.devexpress.com/Blazor/DevExpress.Blazor.Office.IBarItem.GetEnabled) the **Final Save** button.

## Files to Look At

- [Index.razor](./CS/SaveDocuments/Pages/Index.razor)

## Documentation

- [UI Customizatiom](https://docs.devexpress.com/Blazor/DevExpress.Blazor.RichEdit.DxRichEdit#ui-customization)
- [Document Management](https://docs.devexpress.com/Blazor/403344/rich-edit/document-management)
- [Rich Text Editor Examples](https://docs.devexpress.com/Blazor/403343/rich-edit/examples)

## More Examples

- [Rich Edit for Blazor - How to check whether the document is empty](https://github.com/DevExpress-Examples/blazor-dxrichedit-check-if-document-is-empty)
- [Rich Edit for Blazor - How to export a document to a file in HTML format](https://github.com/DevExpress-Examples/blazor-dxrichedit-export-to-html)
