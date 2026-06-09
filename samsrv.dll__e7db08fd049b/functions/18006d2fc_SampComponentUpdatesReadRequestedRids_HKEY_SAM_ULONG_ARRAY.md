# SampComponentUpdatesReadRequestedRids(HKEY__ *,_SAM_ULONG_ARRAY *)

- ea: `0x18006d2fc`
- end: `0x18006d4e0`
- name: `?SampComponentUpdatesReadRequestedRids@@YAJPEAUHKEY__@@PEAU_SAM_ULONG_ARRAY@@@Z`
- size: `484`
- prototype: `__int64 __fastcall(HKEY hKey, struct _SAM_ULONG_ARRAY *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18006f42c`

## callees

- `0x180027e24`
- `0x18002cd80`
- `0x18002d720`
- `0x18006d2fc`
- `0x1800711dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18006d386`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18006d386`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18006d41d`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18006d41d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006d3ac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006d3ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006d481`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006d481`

## pseudocode

```c

```
