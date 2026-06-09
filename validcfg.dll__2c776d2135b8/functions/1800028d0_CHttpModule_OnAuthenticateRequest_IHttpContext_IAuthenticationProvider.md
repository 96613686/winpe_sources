# CHttpModule::OnAuthenticateRequest(IHttpContext *,IAuthenticationProvider *)

- ea: `0x1800028d0`
- end: `0x180002908`
- name: `?OnAuthenticateRequest@CHttpModule@@UEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVIAuthenticationProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800028db`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800028e8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800028f5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800028db`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800028e8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800028f5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800028fb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800028fb`

## pseudocode

```c
__int64 CHttpModule::OnAuthenticateRequest()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CHttpModule::OnAuthenticateRequest");
  OutputDebugStringA(
    " but did not override the method in its CHttpModule implementation.  Please check the method signature to make sure "
    "it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x1800028d0  sub     rsp, 28h
0x1800028d4  lea     rcx, OutputString; "This module subscribed to event "
0x1800028db  call    cs:__imp_OutputDebugStringA
0x1800028e1  lea     rcx, aChttpmoduleOna_2; "CHttpModule::OnAuthenticateRequest"
0x1800028e8  call    cs:__imp_OutputDebugStringA
0x1800028ee  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x1800028f5  call    cs:__imp_OutputDebugStringA
0x1800028fb  call    cs:__imp_DebugBreak
0x180002901  xor     eax, eax
0x180002903  add     rsp, 28h
0x180002907  retn
```
