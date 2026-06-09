# CHttpModule::OnReadEntity(IHttpContext *,IReadEntityProvider *)

- ea: `0x180002e50`
- end: `0x180002e88`
- name: `?OnReadEntity@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIReadEntityProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002e5b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002e68`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002e75`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002e5b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002e68`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002e75`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180002e7b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180002e7b`

## string_xrefs

- `0x180002e61`: `CHttpModule::OnReadEntity`

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
0x180002e50  sub     rsp, 28h
0x180002e54  lea     rcx, OutputString; "This module subscribed to event "
0x180002e5b  call    cs:__imp_OutputDebugStringA
0x180002e61  lea     rcx, aChttpmoduleOnr_0; "CHttpModule::OnReadEntity"
0x180002e68  call    cs:__imp_OutputDebugStringA
0x180002e6e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180002e75  call    cs:__imp_OutputDebugStringA
0x180002e7b  call    cs:__imp_DebugBreak
0x180002e81  xor     eax, eax
0x180002e83  add     rsp, 28h
0x180002e87  retn
```
