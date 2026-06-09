# SampProcessSamKeyUpdates(void *)

- ea: `0x180086ff0`
- end: `0x180087109`
- name: `?SampProcessSamKeyUpdates@@YAJPEAX@Z`
- size: `281`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18007b7d4`

## callees

- `0x180027e24`
- `0x1800372ac`
- `0x180086ff0`
- `0x1800874a0`
- `0x180087a40`
- `0x180087af8`
- `0x180087dac`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800870cc`
- `ntdll!RtlLeaveCriticalSection` at `0x1800870cc`
- `ntdll!RtlEnterCriticalSection` at `0x180086ffb`
- `ntdll!RtlEnterCriticalSection` at `0x180086ffb`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18008701e`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18008701e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800870aa`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800870aa`

## pseudocode

```c

```
