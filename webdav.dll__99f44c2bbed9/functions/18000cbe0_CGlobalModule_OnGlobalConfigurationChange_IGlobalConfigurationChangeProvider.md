# CGlobalModule::OnGlobalConfigurationChange(IGlobalConfigurationChangeProvider *)

- ea: `0x18000cbe0`
- end: `0x18000cc18`
- name: `?OnGlobalConfigurationChange@CGlobalModule@@UEAA?AW4GLOBAL_NOTIFICATION_STATUS@@PEAVIGlobalConfigurationChangeProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cbeb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cbf8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cc05`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cbeb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cbf8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18000cc05`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000cc0b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18000cc0b`

## string_xrefs

- `0x18000cbf1`: `CGlobalModule::OnGlobalConfigurationChange`

## pseudocode

```c
__int64 CGlobalModule::OnGlobalConfigurationChange()
{
  OutputDebugStringA("This module subscribed to event ");
  OutputDebugStringA("CGlobalModule::OnGlobalConfigurationChange");
  OutputDebugStringA(
    " but did not override the method in its CGlobalModule implementation.  Please check the method signature to make sur"
    "e it matches the corresponding method.\n");
  DebugBreak();
  return 0;
}

```

## disassembly

```asm
0x18000cbe0  sub     rsp, 28h
0x18000cbe4  lea     rcx, OutputString; "This module subscribed to event "
0x18000cbeb  call    cs:__imp_OutputDebugStringA
0x18000cbf1  lea     rcx, aCglobalmoduleO_13; "CGlobalModule::OnGlobalConfigurationCha"...
0x18000cbf8  call    cs:__imp_OutputDebugStringA
0x18000cbfe  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x18000cc05  call    cs:__imp_OutputDebugStringA
0x18000cc0b  call    cs:__imp_DebugBreak
0x18000cc11  xor     eax, eax
0x18000cc13  add     rsp, 28h
0x18000cc17  retn
```
