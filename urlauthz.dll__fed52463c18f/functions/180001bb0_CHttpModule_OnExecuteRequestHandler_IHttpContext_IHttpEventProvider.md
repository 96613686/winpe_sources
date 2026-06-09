# CHttpModule::OnExecuteRequestHandler(IHttpContext *,IHttpEventProvider *)

- ea: `0x180001bb0`
- end: `0x180001be8`
- name: `?OnExecuteRequestHandler@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001bbb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001bc8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001bd5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001bbb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001bc8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001bd5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001bdb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001bdb`

## pseudocode

```c
__int64 CHttpModule::OnExecuteRequestHandler()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnExecuteRequestHandler");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180001bb0  sub     rsp, 28h
0x180001bb4  lea     rcx, OutputString; "This module subscribed to event "
0x180001bbb  call    cs:__imp_OutputDebugStringA
0x180001bc1  lea     rcx, aChttpmoduleOne; "CHttpModule::OnExecuteRequestHandler"
0x180001bc8  call    cs:__imp_OutputDebugStringA
0x180001bce  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180001bd5  call    cs:__imp_OutputDebugStringA
0x180001bdb  call    cs:__imp_DebugBreak
0x180001be1  xor     eax, eax
0x180001be3  add     rsp, 28h
0x180001be7  retn
```
