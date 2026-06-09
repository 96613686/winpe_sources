# CHttpModule::OnBeginRequest(IHttpContext *,IHttpEventProvider *)

- ea: `0x180002950`
- end: `0x180002988`
- name: `?OnBeginRequest@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000295b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002968`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002975`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000295b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002968`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002975`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000297b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000297b`

## pseudocode

```c
__int64 CHttpModule::OnBeginRequest()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnBeginRequest");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180002950  sub     rsp, 28h
0x180002954  lea     rcx, OutputString; "This module subscribed to event "
0x18000295b  call    cs:__imp_OutputDebugStringA
0x180002961  lea     rcx, aChttpmoduleOnb; "CHttpModule::OnBeginRequest"
0x180002968  call    cs:__imp_OutputDebugStringA
0x18000296e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180002975  call    cs:__imp_OutputDebugStringA
0x18000297b  call    cs:__imp_DebugBreak
0x180002981  xor     eax, eax
0x180002983  add     rsp, 28h
0x180002987  retn
```
