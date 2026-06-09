# CHttpModule::OnPostAuthorizeRequest(IHttpContext *,IHttpEventProvider *)

- ea: `0x180002b90`
- end: `0x180002bc8`
- name: `?OnPostAuthorizeRequest@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002b9b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002ba8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002bb5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002b9b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002ba8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002bb5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180002bbb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180002bbb`

## pseudocode

```c
__int64 CHttpModule::OnPostAuthorizeRequest()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnPostAuthorizeRequest");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180002b90  sub     rsp, 28h
0x180002b94  lea     rcx, OutputString; "This module subscribed to event "
0x180002b9b  call    cs:__imp_OutputDebugStringA
0x180002ba1  lea     rcx, aChttpmoduleOnp_3; "CHttpModule::OnPostAuthorizeRequest"
0x180002ba8  call    cs:__imp_OutputDebugStringA
0x180002bae  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180002bb5  call    cs:__imp_OutputDebugStringA
0x180002bbb  call    cs:__imp_DebugBreak
0x180002bc1  xor     eax, eax
0x180002bc3  add     rsp, 28h
0x180002bc7  retn
```
