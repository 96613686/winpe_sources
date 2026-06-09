# CleanupSessionDefaultPrinterIfAny

- ea: `0x14005afc0`
- end: `0x14005b0ca`
- name: `CleanupSessionDefaultPrinterIfAny`
- size: `266`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140078ce8`

## callees

- `0x14005983c`
- `0x14005afc0`
- `0x14005b8c0`
- `0x14005be08`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14005b087`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14005b087`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005b09e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005b09e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005b0b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005b0b5`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x14005b06d`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x14005b06d`

## pseudocode

```c

```
