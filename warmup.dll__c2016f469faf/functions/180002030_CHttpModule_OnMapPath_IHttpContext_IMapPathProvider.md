# CHttpModule::OnMapPath(IHttpContext *,IMapPathProvider *)

- ea: `0x180002030`
- end: `0x180002068`
- name: `?OnMapPath@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIMapPathProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000205b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000205b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000203b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002048`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002055`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000203b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002048`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002055`

## string_xrefs

- `0x180002041`: `CHttpModule::OnMapPath`

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
0x180002030  sub     rsp, 28h
0x180002034  lea     rcx, OutputString; "This module subscribed to event "
0x18000203b  call    cs:__imp_OutputDebugStringA
0x180002041  lea     rcx, aChttpmoduleOnm_0; "CHttpModule::OnMapPath"
0x180002048  call    cs:__imp_OutputDebugStringA
0x18000204e  lea     rcx, aButDidNotOverr_0; " but did not override the method in its"...
0x180002055  call    cs:__imp_OutputDebugStringA
0x18000205b  call    cs:__imp_DebugBreak
0x180002061  xor     eax, eax
0x180002063  add     rsp, 28h
0x180002067  retn
```
