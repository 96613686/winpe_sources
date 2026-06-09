# _ExecuteScheduledBackup(ushort const *)

- ea: `0x1800559b0`
- end: `0x180055c9e`
- name: `?_ExecuteScheduledBackup@@YAJPEBG@Z`
- size: `750`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180052a30`

## callees

- `0x1800083a0`
- `0x1800083e4`
- `0x180009d0c`
- `0x1800559b0`
- `0x1800591fc`
- `0x180071194`
- `0x180072e08`
- `0x180072f14`
- `0x18007dfd0`
- `0x18007e314`
- `0x180091600`
- `0x180091a44`
- `0x18009f560`

## import_xrefs

- `KERNEL32!HeapSetInformation` at `0x180055a16`
- `KERNEL32!HeapSetInformation` at `0x180055a16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180055c66`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180055c66`
- `ole32!CoUninitialize` at `0x180055c49`
- `ole32!CoUninitialize` at `0x180055c49`
- `ole32!CoInitializeSecurity` at `0x180055b14`
- `ole32!CoInitializeSecurity` at `0x180055b14`
- `ole32!CoInitializeEx` at `0x180055a79`
- `ole32!CoInitializeEx` at `0x180055a79`

## string_xrefs

- `0x1800559d6`: `_ExecuteScheduledBackup`

## pseudocode

```c

```
