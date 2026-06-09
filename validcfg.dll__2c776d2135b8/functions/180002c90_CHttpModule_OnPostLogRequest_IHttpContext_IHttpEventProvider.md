# CHttpModule::OnPostLogRequest(IHttpContext *,IHttpEventProvider *)

- ea: `0x180002c90`
- end: `0x180002cc8`
- name: `?OnPostLogRequest@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002c9b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002ca8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002cb5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002c9b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002ca8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002cb5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180002cbb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180002cbb`

## pseudocode

```c
__int64 CHttpModule::OnPostLogRequest()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnPostLogRequest");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180002c90  sub     rsp, 28h
0x180002c94  lea     rcx, OutputString; "This module subscribed to event "
0x180002c9b  call    cs:__imp_OutputDebugStringA
0x180002ca1  lea     rcx, aChttpmoduleOnp_11; "CHttpModule::OnPostLogRequest"
0x180002ca8  call    cs:__imp_OutputDebugStringA
0x180002cae  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180002cb5  call    cs:__imp_OutputDebugStringA
0x180002cbb  call    cs:__imp_DebugBreak
0x180002cc1  xor     eax, eax
0x180002cc3  add     rsp, 28h
0x180002cc7  retn
```
