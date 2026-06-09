# CHttpModule::OnReadEntity(IHttpContext *,IReadEntityProvider *)

- ea: `0x18000d1e0`
- end: `0x18000d218`
- name: `?OnReadEntity@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIReadEntityProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d1eb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d1f8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d205`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d1eb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d1f8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000d205`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000d20b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000d20b`

## string_xrefs

- `0x18000d1f1`: `CHttpModule::OnReadEntity`

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
0x18000d1e0  sub     rsp, 28h
0x18000d1e4  lea     rcx, OutputString; "This module subscribed to event "
0x18000d1eb  call    cs:__imp_OutputDebugStringA
0x18000d1f1  lea     rcx, aChttpmoduleOnr_0; "CHttpModule::OnReadEntity"
0x18000d1f8  call    cs:__imp_OutputDebugStringA
0x18000d1fe  lea     rcx, aButDidNotOverr_0; " but did not override the method in its"...
0x18000d205  call    cs:__imp_OutputDebugStringA
0x18000d20b  call    cs:__imp_DebugBreak
0x18000d211  xor     eax, eax
0x18000d213  add     rsp, 28h
0x18000d217  retn
```
