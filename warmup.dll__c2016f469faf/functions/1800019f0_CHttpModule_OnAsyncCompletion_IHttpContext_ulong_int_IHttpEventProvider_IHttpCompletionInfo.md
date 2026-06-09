# CHttpModule::OnAsyncCompletion(IHttpContext *,ulong,int,IHttpEventProvider *,IHttpCompletionInfo *)

- ea: `0x1800019f0`
- end: `0x180001a28`
- name: `?OnAsyncCompletion@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@KHPEAVIHttpEventProvider@@PEAVIHttpCompletionInfo@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001a1b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001a1b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800019fb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001a08`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001a15`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800019fb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001a08`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001a15`

## string_xrefs

- `0x180001a01`: `CHttpModule::OnAsyncCompletion`

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
0x1800019f0  sub     rsp, 28h
0x1800019f4  lea     rcx, OutputString; "This module subscribed to event "
0x1800019fb  call    cs:__imp_OutputDebugStringA
0x180001a01  lea     rcx, aChttpmoduleOna_1; "CHttpModule::OnAsyncCompletion"
0x180001a08  call    cs:__imp_OutputDebugStringA
0x180001a0e  lea     rcx, aButDidNotOverr_0; " but did not override the method in its"...
0x180001a15  call    cs:__imp_OutputDebugStringA
0x180001a1b  call    cs:__imp_DebugBreak
0x180001a21  xor     eax, eax
0x180001a23  add     rsp, 28h
0x180001a27  retn
```
