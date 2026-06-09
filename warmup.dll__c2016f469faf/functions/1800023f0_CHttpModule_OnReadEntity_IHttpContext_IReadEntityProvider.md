# CHttpModule::OnReadEntity(IHttpContext *,IReadEntityProvider *)

- ea: `0x1800023f0`
- end: `0x180002428`
- name: `?OnReadEntity@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIReadEntityProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000241b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000241b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800023fb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002408`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002415`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800023fb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002408`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180002415`

## string_xrefs

- `0x180002401`: `CHttpModule::OnReadEntity`

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
0x1800023f0  sub     rsp, 28h
0x1800023f4  lea     rcx, OutputString; "This module subscribed to event "
0x1800023fb  call    cs:__imp_OutputDebugStringA
0x180002401  lea     rcx, aChttpmoduleOnr_0; "CHttpModule::OnReadEntity"
0x180002408  call    cs:__imp_OutputDebugStringA
0x18000240e  lea     rcx, aButDidNotOverr_0; " but did not override the method in its"...
0x180002415  call    cs:__imp_OutputDebugStringA
0x18000241b  call    cs:__imp_DebugBreak
0x180002421  xor     eax, eax
0x180002423  add     rsp, 28h
0x180002427  retn
```
