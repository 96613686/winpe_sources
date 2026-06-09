# CHttpModule::OnAsyncCompletion(IHttpContext *,ulong,int,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x18000c8a0`
- end: `0x18000c8d8`
- name: `?OnAsyncCompletion@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@KHPEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000c8ab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000c8b8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000c8c5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000c8ab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000c8b8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000c8c5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000c8cb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000c8cb`

## string_xrefs

- `0x18000c8b1`: `CHttpModule::OnAsyncCompletion`

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
0x18000c8a0  sub     rsp, 28h
0x18000c8a4  lea     rcx, OutputString; "This module subscribed to event "
0x18000c8ab  call    cs:__imp_OutputDebugStringA
0x18000c8b1  lea     rcx, aChttpmoduleOna_1; "CHttpModule::OnAsyncCompletion"
0x18000c8b8  call    cs:__imp_OutputDebugStringA
0x18000c8be  lea     rcx, aButDidNotOverr_0; " but did not override the method in its"...
0x18000c8c5  call    cs:__imp_OutputDebugStringA
0x18000c8cb  call    cs:__imp_DebugBreak
0x18000c8d1  xor     eax, eax
0x18000c8d3  add     rsp, 28h
0x18000c8d7  retn
```
