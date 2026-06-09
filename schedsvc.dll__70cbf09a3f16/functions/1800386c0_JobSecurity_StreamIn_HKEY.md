# JobSecurity::StreamIn(HKEY__ *)

- ea: `0x1800386c0`
- end: `0x180038823`
- name: `?StreamIn@JobSecurity@@QEAAJPEAUHKEY__@@@Z`
- size: `355`
- prototype: `int(JobSecurity *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006dd0c`

## callees

- `0x180025040`
- `0x1800386c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180038704`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180038760`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180038704`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180038760`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038776`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800387c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038808`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038776`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800387c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038808`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180038728`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180038728`

## pseudocode

```c

```
