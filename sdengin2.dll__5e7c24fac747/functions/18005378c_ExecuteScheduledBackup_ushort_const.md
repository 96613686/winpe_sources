# _ExecuteScheduledBackup(ushort const *)

- ea: `0x18005378c`
- end: `0x180053a5b`
- name: `?_ExecuteScheduledBackup@@YAJPEBG@Z`
- size: `719`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180050aa0`

## callees

- `0x180008200`
- `0x180008240`
- `0x180009a98`
- `0x18005378c`
- `0x180056d80`
- `0x18006e484`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18007ad90`
- `0x18007b0c8`
- `0x18008d710`
- `0x18008db40`
- `0x18009ae34`

## import_xrefs

- `KERNEL32!HeapSetInformation` at `0x1800537f2`
- `KERNEL32!HeapSetInformation` at `0x1800537f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053a2a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053a2a`
- `ole32!CoUninitialize` at `0x180053a13`
- `ole32!CoUninitialize` at `0x180053a13`
- `ole32!CoInitializeSecurity` at `0x1800538e4`
- `ole32!CoInitializeSecurity` at `0x1800538e4`
- `ole32!CoInitializeEx` at `0x18005384f`
- `ole32!CoInitializeEx` at `0x18005384f`

## string_xrefs

- `0x1800537b2`: `_ExecuteScheduledBackup`

## pseudocode

```c

```
