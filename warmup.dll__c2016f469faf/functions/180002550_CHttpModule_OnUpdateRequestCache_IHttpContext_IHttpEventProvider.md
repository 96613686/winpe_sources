# CHttpModule::OnUpdateRequestCache(IHttpContext *,IHttpEventProvider *)

- ea: `0x180002550`
- end: `0x180002588`
- name: `?OnUpdateRequestCache@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000257b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000257b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000255b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002568`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002575`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000255b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002568`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002575`

## string_xrefs

- `0x180002561`: `CHttpModule::OnUpdateRequestCache`

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
0x180002550  sub     rsp, 28h
0x180002554  lea     rcx, OutputString; "This module subscribed to event "
0x18000255b  call    cs:__imp_OutputDebugStringA
0x180002561  lea     rcx, aChttpmoduleOnu; "CHttpModule::OnUpdateRequestCache"
0x180002568  call    cs:__imp_OutputDebugStringA
0x18000256e  lea     rcx, aButDidNotOverr_0; " but did not override the method in its"...
0x180002575  call    cs:__imp_OutputDebugStringA
0x18000257b  call    cs:__imp_DebugBreak
0x180002581  xor     eax, eax
0x180002583  add     rsp, 28h
0x180002587  retn
```
