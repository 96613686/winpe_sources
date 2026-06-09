# CGlobalModule::OnGlobalCacheCleanup(void)

- ea: `0x180001d30`
- end: `0x180001d68`
- name: `?OnGlobalCacheCleanup@CGlobalModule@@UEAA?AW4GLOBAL_NOTIFICATION_STATUS@@XZ`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001d5b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001d5b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001d3b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001d48`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001d55`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001d3b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001d48`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001d55`

## string_xrefs

- `0x180001d41`: `CGlobalModule::OnGlobalCacheCleanup`

## pseudocode

```c
__int64 CGlobalModule::OnGlobalCacheCleanup()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CGlobalModule::OnGlobalCacheCleanup");
  OutputDebugStringA(
    " but did not override the method in its CGlobalModule implementation.  Please check the method signature to make sur"
    "e it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x180001d30  sub     rsp, 28h
0x180001d34  lea     rcx, OutputString; "This module subscribed to event "
0x180001d3b  call    cs:__imp_OutputDebugStringA
0x180001d41  lea     rcx, aCglobalmoduleO_9; "CGlobalModule::OnGlobalCacheCleanup"
0x180001d48  call    cs:__imp_OutputDebugStringA
0x180001d4e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180001d55  call    cs:__imp_OutputDebugStringA
0x180001d5b  call    cs:__imp_DebugBreak
0x180001d61  xor     eax, eax
0x180001d63  add     rsp, 28h
0x180001d67  retn
```
