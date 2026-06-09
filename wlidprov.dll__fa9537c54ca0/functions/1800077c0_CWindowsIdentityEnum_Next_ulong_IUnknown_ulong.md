# CWindowsIdentityEnum::Next(ulong,IUnknown * *,ulong *)

- ea: `0x1800077c0`
- end: `0x180007e00`
- name: `?Next@CWindowsIdentityEnum@@UEAAJKPEAPEAUIUnknown@@PEAK@Z`
- size: `1600`
- prototype: `__int64 __fastcall(CWindowsIdentityEnum *__hidden this, unsigned int, struct IUnknown **, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800064d8`
- `0x180007170`
- `0x1800077c0`
- `0x1800090c0`
- `0x18000a3a0`
- `0x18000a400`
- `0x18000bcc4`
- `0x18001a0d0`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007996`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800079e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007c7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007cd4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007996`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800079e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007c7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007cd4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000791c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000791c`
- `ntdll!strrchr` at `0x180007846`
- `ntdll!strrchr` at `0x180007a4c`
- `ntdll!strrchr` at `0x180007ab3`
- `ntdll!strrchr` at `0x180007b10`
- `ntdll!strrchr` at `0x180007b70`
- `ntdll!strrchr` at `0x180007bd0`
- `ntdll!strrchr` at `0x180007c30`
- `ntdll!strrchr` at `0x180007846`
- `ntdll!strrchr` at `0x180007a4c`
- `ntdll!strrchr` at `0x180007ab3`
- `ntdll!strrchr` at `0x180007b10`
- `ntdll!strrchr` at `0x180007b70`
- `ntdll!strrchr` at `0x180007bd0`
- `ntdll!strrchr` at `0x180007c30`

## string_xrefs

- `0x1800077fe`: `CWindowsIdentityEnum::Next`

## pseudocode

```c

```
