# CHttpModule::OnUpdateRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x18000d320`
- end: `0x18000d358`
- name: `?OnUpdateRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d32b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d338`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d345`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d32b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d338`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d345`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000d34b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000d34b`

## string_xrefs

- `0x18000d331`: `CHttpModule::OnUpdateRequestCache`

## pseudocode

```c
__int64 CHttpModule::OnUpdateRequestCache()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnUpdateRequestCache");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x18000d320  sub     rsp, 28h
0x18000d324  lea     rcx, OutputString; "This module subscribed to event "
0x18000d32b  call    cs:__imp_OutputDebugStringA
0x18000d331  lea     rcx, aChttpmoduleOnu; "CHttpModule::OnUpdateRequestCache"
0x18000d338  call    cs:__imp_OutputDebugStringA
0x18000d33e  lea     rcx, aButDidNotOverr_0; " but did not override the method in its"...
0x18000d345  call    cs:__imp_OutputDebugStringA
0x18000d34b  call    cs:__imp_DebugBreak
0x18000d351  xor     eax, eax
0x18000d353  add     rsp, 28h
0x18000d357  retn
```
