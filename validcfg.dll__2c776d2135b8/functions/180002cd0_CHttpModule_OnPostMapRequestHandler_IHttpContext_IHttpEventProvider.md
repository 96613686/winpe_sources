# CHttpModule::OnPostMapRequestHandler(IHttpContext *,IHttpEventProvider *)

- ea: `0x180002cd0`
- end: `0x180002d08`
- name: `?OnPostMapRequestHandler@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002cdb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002ce8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002cf5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002cdb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002ce8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002cf5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180002cfb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180002cfb`

## pseudocode

```c
__int64 CHttpModule::OnPostMapRequestHandler()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnPostMapRequestHandler");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180002cd0  sub     rsp, 28h
0x180002cd4  lea     rcx, OutputString; "This module subscribed to event "
0x180002cdb  call    cs:__imp_OutputDebugStringA
0x180002ce1  lea     rcx, aChttpmoduleOnp_9; "CHttpModule::OnPostMapRequestHandler"
0x180002ce8  call    cs:__imp_OutputDebugStringA
0x180002cee  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180002cf5  call    cs:__imp_OutputDebugStringA
0x180002cfb  call    cs:__imp_DebugBreak
0x180002d01  xor     eax, eax
0x180002d03  add     rsp, 28h
0x180002d07  retn
```
