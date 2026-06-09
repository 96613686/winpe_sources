# CHttpModule::OnPostResolveRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180002330`
- end: `0x180002368`
- name: `?OnPostResolveRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000235b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000235b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000233b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002348`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002355`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000233b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002348`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002355`

## string_xrefs

- `0x180002341`: `CHttpModule::OnPostResolveRequestCache`

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
0x180002330  sub     rsp, 28h
0x180002334  lea     rcx, OutputString; "This module subscribed to event "
0x18000233b  call    cs:__imp_OutputDebugStringA
0x180002341  lea     rcx, aChttpmoduleOnp_0; "CHttpModule::OnPostResolveRequestCache"
0x180002348  call    cs:__imp_OutputDebugStringA
0x18000234e  lea     rcx, aButDidNotOverr_0; " but did not override the method in its"...
0x180002355  call    cs:__imp_OutputDebugStringA
0x18000235b  call    cs:__imp_DebugBreak
0x180002361  xor     eax, eax
0x180002363  add     rsp, 28h
0x180002367  retn
```
