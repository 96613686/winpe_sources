# CHttpModule::OnMapPath(IHttpContext *,IMapPathProvider *)

- ea: `0x180002a90`
- end: `0x180002ac8`
- name: `?OnMapPath@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIMapPathProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002a9b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002aa8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002ab5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002a9b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002aa8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002ab5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180002abb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180002abb`

## string_xrefs

- `0x180002aa1`: `CHttpModule::OnMapPath`

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
0x180002a90  sub     rsp, 28h
0x180002a94  lea     rcx, OutputString; "This module subscribed to event "
0x180002a9b  call    cs:__imp_OutputDebugStringA
0x180002aa1  lea     rcx, aChttpmoduleOnm_0; "CHttpModule::OnMapPath"
0x180002aa8  call    cs:__imp_OutputDebugStringA
0x180002aae  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180002ab5  call    cs:__imp_OutputDebugStringA
0x180002abb  call    cs:__imp_DebugBreak
0x180002ac1  xor     eax, eax
0x180002ac3  add     rsp, 28h
0x180002ac7  retn
```
