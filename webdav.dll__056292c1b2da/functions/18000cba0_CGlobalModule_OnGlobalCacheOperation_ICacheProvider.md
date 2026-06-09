# CGlobalModule::OnGlobalCacheOperation(ICacheProvider *)

- ea: `0x18000cba0`
- end: `0x18000cbd8`
- name: `?OnGlobalCacheOperation@CGlobalModule@@UEAA?AW4GLOBAL_NOTIFICATION_STATUS@@PEAVICacheProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cbab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cbb8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cbc5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cbab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cbb8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cbc5`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000cbcb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000cbcb`

## string_xrefs

- `0x18000cbb1`: `CGlobalModule::OnGlobalCacheOperation`

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
0x18000cba0  sub     rsp, 28h
0x18000cba4  lea     rcx, OutputString; "This module subscribed to event "
0x18000cbab  call    cs:__imp_OutputDebugStringA
0x18000cbb1  lea     rcx, aCglobalmoduleO_7; "CGlobalModule::OnGlobalCacheOperation"
0x18000cbb8  call    cs:__imp_OutputDebugStringA
0x18000cbbe  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x18000cbc5  call    cs:__imp_OutputDebugStringA
0x18000cbcb  call    cs:__imp_DebugBreak
0x18000cbd1  xor     eax, eax
0x18000cbd3  add     rsp, 28h
0x18000cbd7  retn
```
