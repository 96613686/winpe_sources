# CGlobalModule::OnGlobalCacheOperation(ICacheProvider *)

- ea: `0x180001d70`
- end: `0x180001da8`
- name: `?OnGlobalCacheOperation@CGlobalModule@@UEAA?AW4GLOBAL_NOTIFICATION_STATUS@@PEAVICacheProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001d9b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001d9b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001d7b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001d88`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001d95`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001d7b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001d88`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001d95`

## string_xrefs

- `0x180001d81`: `CGlobalModule::OnGlobalCacheOperation`

## pseudocode

```c
__int64 CGlobalModule::OnGlobalCacheOperation()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CGlobalModule::OnGlobalCacheOperation");
  OutputDebugStringA(
    " but did not override the method in its CGlobalModule implementation.  Please check the method signature to make sur"
    "e it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180001d70  sub     rsp, 28h
0x180001d74  lea     rcx, OutputString; "This module subscribed to event "
0x180001d7b  call    cs:__imp_OutputDebugStringA
0x180001d81  lea     rcx, aCglobalmoduleO_6; "CGlobalModule::OnGlobalCacheOperation"
0x180001d88  call    cs:__imp_OutputDebugStringA
0x180001d8e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180001d95  call    cs:__imp_OutputDebugStringA
0x180001d9b  call    cs:__imp_DebugBreak
0x180001da1  xor     eax, eax
0x180001da3  add     rsp, 28h
0x180001da7  retn
```
