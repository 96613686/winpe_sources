# GetStringValueFromRegistry

- ea: `0x1400610e4`
- end: `0x1400611f8`
- name: `GetStringValueFromRegistry`
- size: `276`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValue, LPCWSTR)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1400605b8`
- `0x140060c30`
- `0x140060d04`
- `0x140060fb0`

## callees

- `0x140004790`
- `0x1400610e4`
- `0x140061340`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140061196`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400611b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140061196`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400611b9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140061175`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140061175`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400611d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400611d6`

## pseudocode

```c

```
