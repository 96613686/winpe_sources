# CHttpModule::OnMapRequestHandler(IHttpContext *,IMapHandlerProvider *)

- ea: `0x180002ad0`
- end: `0x180002b08`
- name: `?OnMapRequestHandler@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIMapHandlerProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002adb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002ae8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002af5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002adb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002ae8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002af5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180002afb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180002afb`

## pseudocode

```c
__int64 CHttpModule::OnMapRequestHandler()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnMapRequestHandler");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180002ad0  sub     rsp, 28h
0x180002ad4  lea     rcx, OutputString; "This module subscribed to event "
0x180002adb  call    cs:__imp_OutputDebugStringA
0x180002ae1  lea     rcx, aChttpmoduleOnm; "CHttpModule::OnMapRequestHandler"
0x180002ae8  call    cs:__imp_OutputDebugStringA
0x180002aee  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180002af5  call    cs:__imp_OutputDebugStringA
0x180002afb  call    cs:__imp_DebugBreak
0x180002b01  xor     eax, eax
0x180002b03  add     rsp, 28h
0x180002b07  retn
```
