# CHttpModule::OnPostExecuteRequestHandler(IHttpContext *,IHttpEventProvider *)

- ea: `0x180002c50`
- end: `0x180002c88`
- name: `?OnPostExecuteRequestHandler@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIHttpEventProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002c5b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002c68`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002c75`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002c5b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002c68`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002c75`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180002c7b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180002c7b`

## pseudocode

```c
__int64 CHttpModule::OnPostExecuteRequestHandler()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnPostExecuteRequestHandler");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180002c50  sub     rsp, 28h
0x180002c54  lea     rcx, OutputString; "This module subscribed to event "
0x180002c5b  call    cs:__imp_OutputDebugStringA
0x180002c61  lea     rcx, aChttpmoduleOnp_6; "CHttpModule::OnPostExecuteRequestHandle"...
0x180002c68  call    cs:__imp_OutputDebugStringA
0x180002c6e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180002c75  call    cs:__imp_OutputDebugStringA
0x180002c7b  call    cs:__imp_DebugBreak
0x180002c81  xor     eax, eax
0x180002c83  add     rsp, 28h
0x180002c87  retn
```
