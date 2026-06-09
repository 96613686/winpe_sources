# JobSecurity::StreamIn(HKEY__ *)

- ea: `0x18003a550`
- end: `0x18003a6e2`
- name: `?StreamIn@JobSecurity@@QEAAJPEAUHKEY__@@@Z`
- size: `402`
- prototype: `int(JobSecurity *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180071400`

## callees

- `0x18001fe10`
- `0x18003a550`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003a594`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003a5fc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003a594`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003a5fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a618`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a675`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a6be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a618`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a675`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a6be`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003a5be`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003a5be`

## pseudocode

```c

```
