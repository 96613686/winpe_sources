# CHttpModule::OnCustomRequestNotification(IHttpContext *,ICustomNotificationProvider *)

- ea: `0x180001b30`
- end: `0x180001b68`
- name: `?OnCustomRequestNotification@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVICustomNotificationProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001b3b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001b48`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001b55`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001b3b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001b48`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001b55`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001b5b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001b5b`

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
0x180001b30  sub     rsp, 28h
0x180001b34  lea     rcx, OutputString; "This module subscribed to event "
0x180001b3b  call    cs:__imp_OutputDebugStringA
0x180001b41  lea     rcx, aChttpmoduleOnc; "CHttpModule::OnCustomRequestNotificatio"...
0x180001b48  call    cs:__imp_OutputDebugStringA
0x180001b4e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180001b55  call    cs:__imp_OutputDebugStringA
0x180001b5b  call    cs:__imp_DebugBreak
0x180001b61  xor     eax, eax
0x180001b63  add     rsp, 28h
0x180001b67  retn
```
