---
title: helpstringdll attribute
description: The \ helpstringdll\ attribute sets the name of the DLL to use to perform a document string lookup.
ms.assetid: 1b9b962c-c355-4428-b5ea-dc7fd48b50a9
keywords: ["helpstringdll attribute MIDL"]
topic_type:
- apiref
api_name:
- helpstringdll
api_type:
- NA
---

# helpstringdll attribute

The **\[helpstringdll\]** attribute sets the name of the DLL to use to perform a document string lookup.

``` syntax
[
    helpstringdll(help-text-string)
    [, optional-attribute-list]
] 
library library-name
{ 
    library-definition-statements
};
```

## Parameters

<dl> <dt>

*help-text-string* 
</dt> <dd>

A zero-terminated string of characters specifying the fully qualified file name of a DLL.

</dd> <dt>

*optional-attribute-list* 
</dt> <dd>

Other attributes that apply to the library statement as a whole.

</dd> <dt>

*library-name* 
</dt> <dd>

The identifier that software components will use to denote this [**library**](library.md).

</dd> <dt>

*library-definition-statements* 
</dt> <dd>

One or more MIDL statement which define the interface of the [**library**](library.md).

</dd> </dl>

## Remarks

Use the **\[helpstringdll\]** attribute on a library statement to specify, as a character string, the fully qualified file name of a dynamic link library. This allows a user to view a description of the DLL with the object viewer.

Use the **GetDocumentation2** functions in the **ITypeLib2** and **ITypeInfo2** interfaces to retrieve the help string.

## See also

<dl> <dt>

[**library**](library.md)
</dt> <dt>

[ODL File Syntax](df7aa86f-1453-4409-939e-788d469d611e)
</dt> <dt>

[ODL File Example](86d64a4f-08eb-422a-bb1d-dfa868094645)
</dt> <dt>

[Generating a Type Library With MIDL](generating-a-type-library-with-midl-2.md)
</dt> </dl>

 

 



