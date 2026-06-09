# CGlobalModule::OnGlobalCacheCleanup(void)

- ea: `0x18000cb60`
- end: `0x18000cb98`
- name: `?OnGlobalCacheCleanup@CGlobalModule@@UEAA?AW4GLOBAL_NOTIFICATION_STATUS@@XZ`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cb6b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cb78`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cb85`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cb6b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cb78`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cb85`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000cb8b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000cb8b`

## string_xrefs

- `0x18000cb71`: `CGlobalModule::OnGlobalCacheCleanup`

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
0x18000cb60  sub     rsp, 28h
0x18000cb64  lea     rcx, OutputString; "This module subscribed to event "
0x18000cb6b  call    cs:__imp_OutputDebugStringA
0x18000cb71  lea     rcx, aCglobalmoduleO_10; "CGlobalModule::OnGlobalCacheCleanup"
0x18000cb78  call    cs:__imp_OutputDebugStringA
0x18000cb7e  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x18000cb85  call    cs:__imp_OutputDebugStringA
0x18000cb8b  call    cs:__imp_DebugBreak
0x18000cb91  xor     eax, eax
0x18000cb93  add     rsp, 28h
0x18000cb97  retn
```
