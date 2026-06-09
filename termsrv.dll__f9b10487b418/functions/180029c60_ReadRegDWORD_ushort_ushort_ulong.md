# ReadRegDWORD(ushort *,ushort *,ulong *)

- ea: `0x180029c60`
- end: `0x180029d1c`
- name: `?ReadRegDWORD@@YAJPEAG0PEAK@Z`
- size: `188`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180012960`

## callees

- `0x180029c60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180029ce4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180029ce4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029d09`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029d09`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029ca5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180029ca5`

## pseudocode

```c

```
