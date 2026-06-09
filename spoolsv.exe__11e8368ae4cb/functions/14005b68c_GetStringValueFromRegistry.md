# GetStringValueFromRegistry

- ea: `0x14005b68c`
- end: `0x14005b787`
- name: `GetStringValueFromRegistry`
- size: `251`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValue, LPCWSTR)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14005acd4`
- `0x14005b2a0`
- `0x14005b568`
- `0x140078a70`

## callees

- `0x1400041c0`
- `0x14005b68c`
- `0x14005b8c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14005b738`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14005b755`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14005b738`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14005b755`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14005b71d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14005b71d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005b76c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005b76c`

## pseudocode

```c

```
