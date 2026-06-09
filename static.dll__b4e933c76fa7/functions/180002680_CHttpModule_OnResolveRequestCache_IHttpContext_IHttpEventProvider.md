# CHttpModule::OnResolveRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180002680`
- end: `0x1800026b8`
- name: `?OnResolveRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800026ab`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800026ab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000268b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002698`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800026a5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000268b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002698`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800026a5`

## string_xrefs

- `0x180002691`: `CHttpModule::OnResolveRequestCache`

## pseudocode

```c
__int64 CHttpModule::OnResolveRequestCache()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnResolveRequestCache");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180002680  sub     rsp, 28h
0x180002684  lea     rcx, OutputString; "This module subscribed to event "
0x18000268b  call    cs:__imp_OutputDebugStringA
0x180002691  lea     rcx, aChttpmoduleOnr_1; "CHttpModule::OnResolveRequestCache"
0x180002698  call    cs:__imp_OutputDebugStringA
0x18000269e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x1800026a5  call    cs:__imp_OutputDebugStringA
0x1800026ab  call    cs:__imp_DebugBreak
0x1800026b1  xor     eax, eax
0x1800026b3  add     rsp, 28h
0x1800026b7  retn
```
