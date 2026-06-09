# CHttpModule::OnEndRequest(IHttpContext *,IHttpEventProvider *)

- ea: `0x1800029d0`
- end: `0x180002a08`
- name: `?OnEndRequest@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800029db`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800029e8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800029f5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800029db`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800029e8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800029f5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800029fb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800029fb`

## pseudocode

```c
__int64 CHttpModule::OnEndRequest()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnEndRequest");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x1800029d0  sub     rsp, 28h
0x1800029d4  lea     rcx, OutputString; "This module subscribed to event "
0x1800029db  call    cs:__imp_OutputDebugStringA
0x1800029e1  lea     rcx, aChttpmoduleOne_0; "CHttpModule::OnEndRequest"
0x1800029e8  call    cs:__imp_OutputDebugStringA
0x1800029ee  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x1800029f5  call    cs:__imp_OutputDebugStringA
0x1800029fb  call    cs:__imp_DebugBreak
0x180002a01  xor     eax, eax
0x180002a03  add     rsp, 28h
0x180002a07  retn
```
