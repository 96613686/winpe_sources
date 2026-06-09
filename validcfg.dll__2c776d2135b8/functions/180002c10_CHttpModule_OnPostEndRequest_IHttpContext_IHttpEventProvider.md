# CHttpModule::OnPostEndRequest(IHttpContext *,IHttpEventProvider *)

- ea: `0x180002c10`
- end: `0x180002c48`
- name: `?OnPostEndRequest@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002c1b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002c28`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002c35`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002c1b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002c28`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002c35`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180002c3b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180002c3b`

## pseudocode

```c
__int64 CHttpModule::OnPostEndRequest()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnPostEndRequest");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180002c10  sub     rsp, 28h
0x180002c14  lea     rcx, OutputString; "This module subscribed to event "
0x180002c1b  call    cs:__imp_OutputDebugStringA
0x180002c21  lea     rcx, aChttpmoduleOnp_4; "CHttpModule::OnPostEndRequest"
0x180002c28  call    cs:__imp_OutputDebugStringA
0x180002c2e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180002c35  call    cs:__imp_OutputDebugStringA
0x180002c3b  call    cs:__imp_DebugBreak
0x180002c41  xor     eax, eax
0x180002c43  add     rsp, 28h
0x180002c47  retn
```
