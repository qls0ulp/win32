---
title: Text Object Model
description: This section contains information about the programming elements used with the Text Object Model (TOM).
ms.assetid: 'e304ec18-ec2e-4ea7-91c6-6f6ab63b72ae'
---

# Text Object Model

This section contains information about the programming elements used with the Text Object Model (TOM).

The TOM defines a substantial set of text manipulation interfaces. Text solutions such as Microsoft Word and rich edit controls support the TOM feature set. TOM was greatly influenced by WordBasic (the programming language used for Word) and it is easy to use from Microsoft Visual Basic for Applications (VBA). This compatibility has several advantages:

-   Code can migrate fairly easily from one solution to another.
-   One language can be used to share text information between different text engines.
-   It reduces the need for documentation and code compared to the separate low-level Component Object Model (COM) and VBA interfaces.

However, it can be less efficient for C/C++ purposes than the use of more general lower level COM interfaces.

TOM is a straightforward set of interfaces to implement for its primary text solutions, Word and rich edit controls. However, for applications that place minor emphasis on text, it is better to provide TOM interfaces by transferring the text to an edit control that supports TOM. Since rich edit controls ship with Microsoft operating systems, they are the standard means of obtaining TOM functionality.

### Overviews



| Topic                                                          | Contents                                                                                                                                                                                                         |
|----------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [About Text Object Model](about-text-object-model.md)         | The top-level Text Object Model (TOM) object is defined by the [**ITextDocument**](itextdocument.md) interface, which has methods for creating and retrieving objects lower in the object hierarchy.<br/> |
| [Using The Text Object Model](using-the-text-object-model.md) | The code samples in this document show various aspects of using the Text Object Model (TOM).<br/>                                                                                                          |



�

### Interfaces



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Topic</th>
<th>Contents</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>[<strong>ITextDocument</strong>](itextdocument.md)</td>
<td>The [<strong>ITextDocument</strong>](itextdocument.md) interface is the TOM top-level interface, which retrieves the active selection and range objects for any story in the document�whether active or not. It enables the application to:
<ul>
<li>Open and save documents.</li>
<li>Control undo behavior and screen updating.</li>
<li>Find a range from a screen position.</li>
<li>Get an [<strong>ITextStoryRanges</strong>](itextstoryranges.md) story enumerator.</li>
</ul>
<br/> <strong>When to Implement</strong><br/> Applications typically do not implement the [<strong>ITextDocument</strong>](itextdocument.md) interface. Microsoft text solutions, such as rich edit controls, implement <strong>ITextDocument</strong> as part of their TOM implementation. <br/> <strong>When to Use</strong><br/> Applications can retrieve an [<strong>ITextDocument</strong>](itextdocument.md) pointer from a rich edit control. To do this, send an [<strong>EM_GETOLEINTERFACE</strong>](em-getoleinterface.md) message to retrieve an [<strong>IRichEditOle</strong>](iricheditole.md) object from a rich edit control. Then, call the object's [<strong>IUnknown::QueryInterface</strong>](https://msdn.microsoft.com/library/windows/desktop/ms682521) method to retrieve an <strong>ITextDocument</strong> pointer.<br/></td>
</tr>
<tr class="even">
<td>[<strong>ITextFont</strong>](itextfont.md)</td>
<td>TOM rich text-range attributes are accessed through a pair of dual interfaces, [<strong>ITextFont</strong>](itextfont.md) and [<strong>ITextPara</strong>](itextpara.md).<br/></td>
</tr>
<tr class="odd">
<td>[<strong>ITextPara</strong>](itextpara.md)</td>
<td>TOM rich text-range attributes are accessed through a pair of dual interfaces, [<strong>ITextFont</strong>](itextfont.md) and [<strong>ITextPara</strong>](itextpara.md).<br/></td>
</tr>
<tr class="even">
<td>[<strong>ITextRange</strong>](itextrange.md)</td>
<td>The [<strong>ITextRange</strong>](itextrange.md) objects are powerful editing and data-binding tools that allow a program to select text in a story and then examine or change that text.<br/></td>
</tr>
<tr class="odd">
<td>[<strong>ITextSelection</strong>](itextselection.md)</td>
<td>A text selection is a text range with selection highlighting.<br/></td>
</tr>
<tr class="even">
<td>[<strong>ITextStoryRanges</strong>](itextstoryranges.md)</td>
<td>The purpose of the [<strong>ITextStoryRanges</strong>](itextstoryranges.md) interface is to enumerate the stories in an [<strong>ITextDocument</strong>](itextdocument.md).<br/></td>
</tr>
</tbody>
</table>



�

�

�




