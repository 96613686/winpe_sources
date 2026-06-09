# CleanupSessionDefaultPrinterIfAny

- ea: `0x1400608d8`
- end: `0x1400609fb`
- name: `CleanupSessionDefaultPrinterIfAny`
- size: `291`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14008016c`

## callees

- `0x14005f014`
- `0x1400608d8`
- `0x140061340`
- `0x1400618f8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400609a5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400609a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400609c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400609c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400609df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400609df`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x140060985`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x140060985`

## pseudocode

```c

```
