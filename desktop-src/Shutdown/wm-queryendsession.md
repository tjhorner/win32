---
Description: The WM\_QUERYENDSESSION message is sent when the user chooses to end the session or when an application calls one of the system shutdown functions.
ms.assetid: 7ad73444-f1f6-4b73-8450-0580b146a5a6
title: WM\_QUERYENDSESSION message
ms.technology: desktop
ms.prod: windows
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# WM\_QUERYENDSESSION message

The **WM\_QUERYENDSESSION** message is sent when the user chooses to end the session or when an application calls one of the system shutdown functions. If any application returns zero, the session is not ended. The system stops sending **WM\_QUERYENDSESSION** messages as soon as one application returns zero.

After processing this message, the system sends the [**WM\_ENDSESSION**](wm-endsession.md) message with the *wParam* parameter set to the results of the **WM\_QUERYENDSESSION** message.

A window receives this message through its [**WindowProc**](https://www.bing.com/search?q=**WindowProc**) function.


```C++
LRESULT CALLBACK WindowProc( 
  HWND hwnd,      // handle to window 
  UINT uMsg,      // message identifier 
  WPARAM wParam,  // not used 
  LPARAM lParam   // logoff option
);
```



## Parameters

<dl> <dt>

*hwnd* 
</dt> <dd>

A handle to the window.

</dd> <dt>

*uMsg* 
</dt> <dd>

The **WM\_QUERYENDSESSION** identifier.

</dd> <dt>

*wParam* 
</dt> <dd>

This parameter is reserved for future use.

</dd> <dt>

*lParam* 
</dt> <dd>

This parameter can be one or more of the following values. If this parameter is 0, the system is shutting down or restarting (it is not possible to determine which event is occurring).



| Value                                                                                                                                                                                                                                           | Meaning                                                                                                                                                                                                                         |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span id="ENDSESSION_CLOSEAPP"></span><span id="endsession_closeapp"></span><dl> <dt>**ENDSESSION\_CLOSEAPP**</dt> <dt>0x00000001</dt> </dl> | The application is using a file that must be replaced, the system is being serviced, or system resources are exhausted. For more information, see [Guidelines for Applications](https://msdn.microsoft.com/97b1df63-65a9-47b4-891b-e4a754882b89).<br/> |
| <span id="ENDSESSION_CRITICAL"></span><span id="endsession_critical"></span><dl> <dt>**ENDSESSION\_CRITICAL**</dt> <dt>0x40000000</dt> </dl> | The application is forced to shut down.<br/>                                                                                                                                                                              |
| <span id="ENDSESSION_LOGOFF"></span><span id="endsession_logoff"></span><dl> <dt>**ENDSESSION\_LOGOFF**</dt> <dt>0x80000000</dt> </dl>       | The user is logging off. For more information, see [Logging Off](logging-off.md).<br/>                                                                                                                                   |



 

Note that this parameter is a bit mask. To test for this value, use a bit-wise operation; do not test for equality.

</dd> </dl>

## Return value

Applications should respect the user's intentions and return **TRUE**. By default, the [**DefWindowProc**](https://www.bing.com/search?q=**DefWindowProc**) function returns **TRUE** for this message.

If shutting down would corrupt the system or media that is being burned, the application can return **FALSE**. However, it is good practice to respect the user's actions.

## Remarks

When an application returns **TRUE** for this message, it receives the [**WM\_ENDSESSION**](wm-endsession.md) message, regardless of how the other applications respond to the **WM\_QUERYENDSESSION** message. Each application should return **TRUE** or **FALSE** immediately upon receiving this message, and defer any cleanup operations until it receives the **WM\_ENDSESSION** message.

Applications can display a user interface prompting the user for information at shutdown, however it is not recommended. After five seconds, the system displays information about the applications that are preventing shutdown and allows the user to terminate them. For example, Windows XP displays a dialog box, while Windows Vista displays a full screen with additional information about the applications blocking shutdown. If your application must block or postpone system shutdown, use the [**ShutdownBlockReasonCreate**](/windows/desktop/api/Winuser/nf-winuser-shutdownblockreasoncreate) function. For more information, see [Shutdown Changes for Windows Vista](shutdown-changes-for-windows-vista.md).

Console applications can use the [**SetConsoleCtrlHandler**](https://www.bing.com/search?q=**SetConsoleCtrlHandler**) function to receive shutdown notification.

Service applications can use the [**RegisterServiceCtrlHandlerEx**](https://msdn.microsoft.com/23eea346-9899-4214-88f4-9b7eb7ce1332) function to receive shutdown notifications in a handler routine.

## Examples

For an example, see [Logging Off](logging-off.md).

## Requirements



|                                     |                                                                                                          |
|-------------------------------------|----------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows XP \[desktop apps \| UWP apps\]<br/>                                                       |
| Minimum supported server<br/> | Windows Server 2003 \[desktop apps \| UWP apps\]<br/>                                              |
| Header<br/>                   | <dl> <dt>WinUser.h (include Windows.h)</dt> </dl> |



## See also

<dl> <dt>

[Logging Off](logging-off.md)
</dt> <dt>

[Shutting Down](shutting-down.md)
</dt> <dt>

[**DefWindowProc**](https://www.bing.com/search?q=**DefWindowProc**)
</dt> <dt>

[**ExitWindows**](/windows/desktop/api/Winuser/nf-winuser-exitwindows)
</dt> <dt>

[**SetProcessShutdownParameters**](https://msdn.microsoft.com/c467950e-31e1-4608-a08a-0736a5524e0e)
</dt> <dt>

[**WM\_ENDSESSION**](wm-endsession.md)
</dt> </dl>

 

 



