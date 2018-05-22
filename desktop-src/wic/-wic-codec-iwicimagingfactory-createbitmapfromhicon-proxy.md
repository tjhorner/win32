---
Description: 'Proxy function for the CreateBitmapFromHICON method.'
ms.assetid: '5df3d9d9-1b23-4f38-b97e-0b77d6db99d8'
title: 'IWICImagingFactory\_CreateBitmapFromHICON\_Proxy function'
---

# IWICImagingFactory\_CreateBitmapFromHICON\_Proxy function

Proxy function for the [**CreateBitmapFromHICON**](-wic-codec-iwicimagingfactory-createbitmapfromhicon.md) method.

## Syntax


```C++
HRESULT IWICImagingFactory_CreateBitmapFromHICON_Proxy(
  _In_��IWICImagingFactory *pFactory,
  _In_��HICON �������������hIcon,
  _Out_�IWICBitmap ��������**ppIBitmap
);
```



## Parameters

<dl> <dt>

*pFactory* \[in\]
</dt> <dd>

Type: **[**IWICImagingFactory**](-wic-codec-iwicimagingfactory.md)\***

</dd> <dt>

*hIcon* \[in\]
</dt> <dd>

Type: **HICON**

The icon handle to create the new bitmap from.

</dd> <dt>

*ppIBitmap* \[out\]
</dt> <dd>

Type: **[**IWICBitmap**](-wic-codec-iwicbitmap.md)\*\***

A pointer that receives a pointer to the new bitmap.

</dd> </dl>

## Return value

Type: **HRESULT**

If this function succeeds, it returns **S\_OK**. Otherwise, it returns an **HRESULT** error code.

## Remarks

## Requirements



|                                     |                                                                                                                                                                  |
|-------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows�XP with SP2, Windows�Vista \[desktop apps only\]<br/>                                                                                              |
| Minimum supported server<br/> | Windows Server�2008 \[desktop apps only\]<br/>                                                                                                             |
| DLL<br/>                      | <dl> <dt>Windowscodecs.dll; </dt> <dt>Wincodec.lib</dt> </dl> |



�

�



