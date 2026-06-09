# CHttpModule::OnAsyncCompletion(IHttpContext *,ulong,int,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x180002890`
- end: `0x1800028c8`
- name: `?OnAsyncCompletion@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@KHPEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000289b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800028a8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800028b5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000289b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800028a8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800028b5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800028bb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800028bb`

## string_xrefs

- `0x1800028a1`: `CHttpModule::OnAsyncCompletion`

## pseudocode

```c
__int64 CHttpModule::OnAsyncCompletion()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnAsyncCompletion");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180002890  sub     rsp, 28h
0x180002894  lea     rcx, OutputString; "This module subscribed to event "
0x18000289b  call    cs:__imp_OutputDebugStringA
0x1800028a1  lea     rcx, aChttpmoduleOna_1; "CHttpModule::OnAsyncCompletion"
0x1800028a8  call    cs:__imp_OutputDebugStringA
0x1800028ae  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x1800028b5  call    cs:__imp_OutputDebugStringA
0x1800028bb  call    cs:__imp_DebugBreak
0x1800028c1  xor     eax, eax
0x1800028c3  add     rsp, 28h
0x1800028c7  retn
```
