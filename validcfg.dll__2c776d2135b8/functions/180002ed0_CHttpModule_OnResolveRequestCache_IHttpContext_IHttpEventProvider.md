# CHttpModule::OnResolveRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180002ed0`
- end: `0x180002f08`
- name: `?OnResolveRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002edb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002ee8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002ef5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002edb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002ee8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002ef5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180002efb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180002efb`

## string_xrefs

- `0x180002ee1`: `CHttpModule::OnResolveRequestCache`

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
0x180002ed0  sub     rsp, 28h
0x180002ed4  lea     rcx, OutputString; "This module subscribed to event "
0x180002edb  call    cs:__imp_OutputDebugStringA
0x180002ee1  lea     rcx, aChttpmoduleOnr_1; "CHttpModule::OnResolveRequestCache"
0x180002ee8  call    cs:__imp_OutputDebugStringA
0x180002eee  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180002ef5  call    cs:__imp_OutputDebugStringA
0x180002efb  call    cs:__imp_DebugBreak
0x180002f01  xor     eax, eax
0x180002f03  add     rsp, 28h
0x180002f07  retn
```
