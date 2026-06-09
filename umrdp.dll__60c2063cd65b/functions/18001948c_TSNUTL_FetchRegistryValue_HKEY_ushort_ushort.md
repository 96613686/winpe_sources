# TSNUTL_FetchRegistryValue(HKEY__ *,ushort *,ushort * *)

- ea: `0x18001948c`
- end: `0x18001958c`
- name: `?TSNUTL_FetchRegistryValue@@YAHPEAUHKEY__@@PEAGPEAPEAG@Z`
- size: `256`
- prototype: `__int64 __fastcall(HKEY hkey, LPCWSTR lpValue, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800165c8`

## callees

- `0x1800090b0`
- `0x18001948c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019559`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019559`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001950f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019571`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001950f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019571`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800194f2`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800194f2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800194c5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001954f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800194c5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001954f`

## pseudocode

```c

```
