---
Description: 'Specifies the slice control mode. Valid values are 0, 1, and 2.'
ms.assetid: '5269DB79-639C-4F67-B885-BF1274CDB635'
title: 'CODECAPI\_AVEncSliceControlMode property'
---

# CODECAPI\_AVEncSliceControlMode property

Specifies the slice control mode. Valid values are 0, 1, and 2.

## Data type

**ULONG** (VT\_UI4)

## Property GUID

**CODECAPI\_AVEncSliceControlMode**

## Property value

Slice control mode values:



| Value                                                                        | Meaning                                                                                                                                                                                                 |
|------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <dl> <dt>0</dt> </dl> | Setting this value to 0 indicates that the [CODECAPI\_AVEncSliceControlSize](codecapi-avencslicecontrolsize.md) property will specify the slice size in units of macroblocks per slice.<br/>     |
| <dl> <dt>1</dt> </dl> | Setting this value to 1 indicates that the [CODECAPI\_AVEncSliceControlSize](codecapi-avencslicecontrolsize.md) property will specify the slice size in units of bits per slice.<br/>            |
| <dl> <dt>2</dt> </dl> | Setting this value to 2 indicates that the [CODECAPI\_AVEncSliceControlSize](codecapi-avencslicecontrolsize.md) property will specify the slice size in units of macroblock rows per slice.<br/> |



�

The encoder returns the values that it supports.

## Remarks

**H.264/AVC encoders:**

It is recommended that the encoder supports [**GetValue**](imfmediaevent-getvalue.md), [**SetValue**](https://msdn.microsoft.com/library/windows/desktop/dd311966), and [**GetParameterRange**](https://msdn.microsoft.com/library/windows/desktop/dd311956).

If [**SetValue**](https://msdn.microsoft.com/library/windows/desktop/dd311966) is not called for CODECAPI\_AVEncSliceControlMode, [**GetValue**](imfmediaevent-getvalue.md) for CODECAPI\_AVEncSliceControlMode can return **VFW\_E\_CODECAPI\_NO\_CURRENT\_VALUE**. [**GetDefaultValue**](https://msdn.microsoft.com/library/windows/desktop/dd311955) may return **VFW\_E\_CODECAPI\_NO\_DEFAULT** for CODECAPI\_AVEncSliceControlMode.

Recommended default value is 2 (size in MB row per slice).

This is a static API, which means the application won�t change this while the encoder is running.

## Examples


```C++
if (pCodecAPI->IsSupported(&amp;CODECAPI_AVEncSliceControlMode) == S_OK) {                
     VARIANT var;
     var.vt = VT_UI4;
     var.ulVal =ulSliceMode;
     pCodecAPI->SetValue(&amp;CODECAPI_AVEncSliceControlMode, &amp;var);
}
```



## Requirements



|                                     |                                                                                       |
|-------------------------------------|---------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows�8.1 \[desktop apps \| UWP apps\]<br/>                                   |
| Minimum supported server<br/> | Windows Server�2012�R2 \[desktop apps \| UWP apps\]<br/>                        |
| Header<br/>                   | <dl> <dt>Codecapi.h</dt> </dl> |



## See also

<dl> <dt>

[Media Foundation Properties](media-foundation-properties.md)
</dt> </dl>

�

�



