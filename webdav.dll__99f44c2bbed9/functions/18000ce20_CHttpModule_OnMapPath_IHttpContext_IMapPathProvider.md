# CHttpModule::OnMapPath(IHttpContext *,IMapPathProvider *)

- ea: `0x18000ce20`
- end: `0x18000ce58`
- name: `?OnMapPath@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIMapPathProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000ce2b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000ce38`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000ce45`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000ce2b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000ce38`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000ce45`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000ce4b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000ce4b`

## string_xrefs

- `0x18000ce31`: `CHttpModule::OnMapPath`

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
0x18000ce20  sub     rsp, 28h
0x18000ce24  lea     rcx, OutputString; "This module subscribed to event "
0x18000ce2b  call    cs:__imp_OutputDebugStringA
0x18000ce31  lea     rcx, aChttpmoduleOnm_0; "CHttpModule::OnMapPath"
0x18000ce38  call    cs:__imp_OutputDebugStringA
0x18000ce3e  lea     rcx, aButDidNotOverr_0; " but did not override the method in its"...
0x18000ce45  call    cs:__imp_OutputDebugStringA
0x18000ce4b  call    cs:__imp_DebugBreak
0x18000ce51  xor     eax, eax
0x18000ce53  add     rsp, 28h
0x18000ce57  retn
```
