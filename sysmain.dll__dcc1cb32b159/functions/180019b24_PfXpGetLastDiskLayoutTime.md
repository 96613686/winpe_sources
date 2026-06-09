# PfXpGetLastDiskLayoutTime

- ea: `0x180019b24`
- end: `0x180019bf2`
- name: `PfXpGetLastDiskLayoutTime`
- size: `206`
- prototype: `__int64 __fastcall(FILETIME *lpFileTime1)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018ec0`

## callees

- `0x180019b24`
- `0x1800b64c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019b82`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019b82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019bbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019bbb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180019ba3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180019ba3`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180019bca`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180019bca`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180019bb1`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180019bb1`

## pseudocode

```c

```
