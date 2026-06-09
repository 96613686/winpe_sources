# CGlobalModule::OnGlobalConfigurationChange(IGlobalConfigurationChangeProvider *)

- ea: `0x180001db0`
- end: `0x180001de8`
- name: `?OnGlobalConfigurationChange@CGlobalModule@@UEAA?AW4GLOBAL_NOTIFICATION_STATUS@@PEAVIGlobalConfigurationChangeProvider@@@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001ddb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180001ddb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001dbb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001dc8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001dd5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001dbb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001dc8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180001dd5`

## string_xrefs

- `0x180001dc1`: `CGlobalModule::OnGlobalConfigurationChange`

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
0x180001db0  sub     rsp, 28h
0x180001db4  lea     rcx, OutputString; "This module subscribed to event "
0x180001dbb  call    cs:__imp_OutputDebugStringA
0x180001dc1  lea     rcx, aCglobalmoduleO_12; "CGlobalModule::OnGlobalConfigurationCha"...
0x180001dc8  call    cs:__imp_OutputDebugStringA
0x180001dce  lea     rcx, aButDidNotOverr; " but did not override the method in its"...
0x180001dd5  call    cs:__imp_OutputDebugStringA
0x180001ddb  call    cs:__imp_DebugBreak
0x180001de1  xor     eax, eax
0x180001de3  add     rsp, 28h
0x180001de7  retn
```
