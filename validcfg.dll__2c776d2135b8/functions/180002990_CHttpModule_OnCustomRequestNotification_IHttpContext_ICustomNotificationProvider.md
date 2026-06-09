# CHttpModule::OnCustomRequestNotification(IHttpContext *,ICustomNotificationProvider *)

- ea: `0x180002990`
- end: `0x1800029c8`
- name: `?OnCustomRequestNotification@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVICustomNotificationProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000299b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800029a8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800029b5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000299b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800029a8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800029b5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800029bb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800029bb`

## pseudocode

```c
__int64 CHttpModule::OnCustomRequestNotification()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnCustomRequestNotification");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180002990  sub     rsp, 28h
0x180002994  lea     rcx, OutputString; "This module subscribed to event "
0x18000299b  call    cs:__imp_OutputDebugStringA
0x1800029a1  lea     rcx, aChttpmoduleOnc; "CHttpModule::OnCustomRequestNotificatio"...
0x1800029a8  call    cs:__imp_OutputDebugStringA
0x1800029ae  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x1800029b5  call    cs:__imp_OutputDebugStringA
0x1800029bb  call    cs:__imp_DebugBreak
0x1800029c1  xor     eax, eax
0x1800029c3  add     rsp, 28h
0x1800029c7  retn
```
