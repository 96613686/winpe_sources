# CHttpModule::OnPostResolveRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x18000d120`
- end: `0x18000d158`
- name: `?OnPostResolveRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d12b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d138`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d145`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d12b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d138`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d145`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000d14b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000d14b`

## string_xrefs

- `0x18000d131`: `CHttpModule::OnPostResolveRequestCache`

## pseudocode

```c
__int64 CHttpModule::OnPostResolveRequestCache()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnPostResolveRequestCache");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x18000d120  sub     rsp, 28h
0x18000d124  lea     rcx, OutputString; "This module subscribed to event "
0x18000d12b  call    cs:__imp_OutputDebugStringA
0x18000d131  lea     rcx, aChttpmoduleOnp_0; "CHttpModule::OnPostResolveRequestCache"
0x18000d138  call    cs:__imp_OutputDebugStringA
0x18000d13e  lea     rcx, aButDidNotOverr_0; " but did not override the method in its"...
0x18000d145  call    cs:__imp_OutputDebugStringA
0x18000d14b  call    cs:__imp_DebugBreak
0x18000d151  xor     eax, eax
0x18000d153  add     rsp, 28h
0x18000d157  retn
```
