# CHttpModule::OnReadEntity(IHttpContext *,IReadEntityProvider *)

- ea: `0x1800025e0`
- end: `0x180002618`
- name: `?OnReadEntity@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIReadEntityProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000260b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000260b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800025eb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800025f8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002605`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800025eb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800025f8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002605`

## string_xrefs

- `0x1800025f1`: `CHttpModule::OnReadEntity`

## pseudocode

```c
__int64 CHttpModule::OnReadEntity()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnReadEntity");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x1800025e0  sub     rsp, 28h
0x1800025e4  lea     rcx, OutputString; "This module subscribed to event "
0x1800025eb  call    cs:__imp_OutputDebugStringA
0x1800025f1  lea     rcx, aChttpmoduleOnr_0; "CHttpModule::OnReadEntity"
0x1800025f8  call    cs:__imp_OutputDebugStringA
0x1800025fe  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180002605  call    cs:__imp_OutputDebugStringA
0x18000260b  call    cs:__imp_DebugBreak
0x180002611  xor     eax, eax
0x180002613  add     rsp, 28h
0x180002617  retn
```
