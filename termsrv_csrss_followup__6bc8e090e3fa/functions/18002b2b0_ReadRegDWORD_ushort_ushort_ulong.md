# ReadRegDWORD(ushort *,ushort *,ulong *)

- ea: `0x18002b2b0`
- end: `0x18002b37f`
- name: `?ReadRegDWORD@@YAJPEAG0PEAK@Z`
- size: `207`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800131c0`

## callees

- `0x18002b2b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002b33a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002b33a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b365`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b365`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b2f5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b2f5`

## pseudocode

```c

```
