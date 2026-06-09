# CreateDeviceLogicalUnit(ushort const *,ulong,ushort const *,_GUID const *,char const *,ulong,_GUID const *)

- ea: `0x1400974e0`
- end: `0x14009773e`
- name: `?CreateDeviceLogicalUnit@@YAPEAXPEBGK0PEBU_GUID@@PEBDK1@Z`
- size: `606`
- prototype: `void *__fastcall(const unsigned __int16 *, unsigned int, const unsigned __int16 *, const struct _GUID *, const char *, unsigned int, const struct _GUID *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x14009584c`

## callees

- `0x1400042b0`
- `0x140055f4c`
- `0x140096da8`
- `0x140097018`
- `0x1400974e0`
- `0x14011ea40`
- `0x14011f6fc`
- `0x14011f868`
- `0x1401a5b20`
- `0x1401a5cb0`
- `0x1401a6470`
- `0x1401a6608`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400976fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400976fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400976cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400976cc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400975c5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400975c5`

## string_xrefs

- `0x140097529`: `VstorCreateDeviceLogicalUnit`
- `0x140097557`: `VhdSetUtilities::OpenStorageLogicalUnit`
- `0x14009768f`: `VhdSetUtilities::OpenStorageLogicalUnit`

## pseudocode

```c

```
