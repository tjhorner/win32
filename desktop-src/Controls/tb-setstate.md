---
title: TB\_SETSTATE message
description: Sets the state for the specified button in a toolbar.
ms.assetid: '68633b58-8d21-4931-b01f-32a66bda37b1'
keywords: ["TB_SETSTATE message Windows Controls"]
topic_type:
- apiref
api_name:
- TB_SETSTATE
api_location:
- Commctrl.h
api_type:
- HeaderDef
---

# TB\_SETSTATE message

Sets the state for the specified button in a toolbar.

## Parameters

<dl> <dt>

*wParam* 
</dt> <dd>

Command identifier of the button.

</dd> <dt>

*lParam* 
</dt> <dd>

The [**LOWORD**](https://msdn.microsoft.com/library/windows/desktop/ms632659) is a combination of values listed in [Toolbar Button States](toolbar-button-states.md). The [**HIWORD**](https://msdn.microsoft.com/library/windows/desktop/ms632657) must be zero.

</dd> </dl>

## Return value

Returns **TRUE** if successful, or **FALSE** otherwise.

## Requirements



|                                     |                                                                                       |
|-------------------------------------|---------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows�Vista \[desktop apps only\]<br/>                                        |
| Minimum supported server<br/> | Windows Server�2003 \[desktop apps only\]<br/>                                  |
| Header<br/>                   | <dl> <dt>Commctrl.h</dt> </dl> |



�

�




