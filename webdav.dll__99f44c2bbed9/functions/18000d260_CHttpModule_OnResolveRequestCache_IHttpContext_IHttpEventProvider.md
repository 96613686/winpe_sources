# CHttpModule::OnResolveRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x18000d260`
- end: `0x18000d298`
- name: `?OnResolveRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d26b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d278`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d285`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d26b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d278`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d285`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000d28b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000d28b`

## string_xrefs

- `0x18000d271`: `CHttpModule::OnResolveRequestCache`

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
0x18000d260  sub     rsp, 28h
0x18000d264  lea     rcx, OutputString; "This module subscribed to event "
0x18000d26b  call    cs:__imp_OutputDebugStringA
0x18000d271  lea     rcx, aChttpmoduleOnr_1; "CHttpModule::OnResolveRequestCache"
0x18000d278  call    cs:__imp_OutputDebugStringA
0x18000d27e  lea     rcx, aButDidNotOverr_0; " but did not override the method in its"...
0x18000d285  call    cs:__imp_OutputDebugStringA
0x18000d28b  call    cs:__imp_DebugBreak
0x18000d291  xor     eax, eax
0x18000d293  add     rsp, 28h
0x18000d297  retn
```
