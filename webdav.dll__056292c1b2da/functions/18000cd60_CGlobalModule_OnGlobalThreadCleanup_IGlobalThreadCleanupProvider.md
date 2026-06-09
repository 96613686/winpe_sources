# CGlobalModule::OnGlobalThreadCleanup(IGlobalThreadCleanupProvider *)

- ea: `0x18000cd60`
- end: `0x18000cd98`
- name: `?OnGlobalThreadCleanup@CGlobalModule@@UEAA?AW4GLOBAL_NOTIFICATION_STATUS@@PEAVIGlobalThreadCleanupProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cd6b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cd78`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cd85`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cd6b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cd78`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cd85`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000cd8b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000cd8b`

## string_xrefs

- `0x18000cd71`: `CGlobalModule::OnGlobalThreadCleanup`

## pseudocode

```c
__int64 CGlobalModule::OnGlobalThreadCleanup()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CGlobalModule::OnGlobalThreadCleanup");
  OutputDebugStringA(
    " but did not override the method in its CGlobalModule implementation.  Please check the method signature to make sur"
    "e it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x18000cd60  sub     rsp, 28h
0x18000cd64  lea     rcx, OutputString; "This module subscribed to event "
0x18000cd6b  call    cs:__imp_OutputDebugStringA
0x18000cd71  lea     rcx, aCglobalmoduleO_0; "CGlobalModule::OnGlobalThreadCleanup"
0x18000cd78  call    cs:__imp_OutputDebugStringA
0x18000cd7e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x18000cd85  call    cs:__imp_OutputDebugStringA
0x18000cd8b  call    cs:__imp_DebugBreak
0x18000cd91  xor     eax, eax
0x18000cd93  add     rsp, 28h
0x18000cd97  retn
```
