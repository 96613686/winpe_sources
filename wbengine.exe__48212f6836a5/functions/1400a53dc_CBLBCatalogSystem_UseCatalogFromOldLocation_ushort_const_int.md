# CBLBCatalogSystem::_UseCatalogFromOldLocation(ushort const *,int &)

- ea: `0x1400a53dc`
- end: `0x1400a577d`
- name: `?_UseCatalogFromOldLocation@CBLBCatalogSystem@@AEAAJPEBGAEAH@Z`
- size: `929`
- prototype: `int(CBLBCatalogSystem *__hidden this, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, service_task`

## callers

- `0x1400a1be0`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x140014200`
- `0x140014260`
- `0x14003c54c`
- `0x14008863c`
- `0x140088d0c`
- `0x1400a4a30`
- `0x1400a53dc`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1400a54b9`
- `KERNEL32!CreateFileW` at `0x1400a54b9`
- `KERNEL32!CloseHandle` at `0x1400a5525`
- `KERNEL32!CloseHandle` at `0x1400a5582`
- `KERNEL32!CloseHandle` at `0x1400a563a`
- `KERNEL32!CloseHandle` at `0x1400a5525`
- `KERNEL32!CloseHandle` at `0x1400a5582`
- `KERNEL32!CloseHandle` at `0x1400a563a`
- `KERNEL32!GetLastError` at `0x1400a54cd`
- `KERNEL32!GetLastError` at `0x1400a54cd`
- `ole32!CoTaskMemFree` at `0x1400a5719`
- `ole32!CoTaskMemFree` at `0x1400a572e`
- `ole32!CoTaskMemFree` at `0x1400a5719`
- `ole32!CoTaskMemFree` at `0x1400a572e`

## string_xrefs

- `0x1400a5435`: `wcsPath`

## pseudocode

```c

```
