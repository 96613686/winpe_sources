# CHttpModule::OnMapPath(IHttpContext *,IMapPathProvider *)

- ea: `0x180001c30`
- end: `0x180001c68`
- name: `?OnMapPath@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIMapPathProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001c3b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001c48`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001c55`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001c3b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001c48`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001c55`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001c5b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001c5b`

## string_xrefs

- `0x180001c41`: `CHttpModule::OnMapPath`

## pseudocode

```c
__int64 CHttpModule::OnMapPath()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnMapPath");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180001c30  sub     rsp, 28h
0x180001c34  lea     rcx, OutputString; "This module subscribed to event "
0x180001c3b  call    cs:__imp_OutputDebugStringA
0x180001c41  lea     rcx, aChttpmoduleOnm_0; "CHttpModule::OnMapPath"
0x180001c48  call    cs:__imp_OutputDebugStringA
0x180001c4e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180001c55  call    cs:__imp_OutputDebugStringA
0x180001c5b  call    cs:__imp_DebugBreak
0x180001c61  xor     eax, eax
0x180001c63  add     rsp, 28h
0x180001c67  retn
```
