# CreateDeviceLogicalUnit(ushort const *,ulong,ushort const *,_GUID const *,char const *,ulong,_GUID const *)

- ea: `0x140116f94`
- end: `0x1401171f2`
- name: `?CreateDeviceLogicalUnit@@YAPEAXPEBGK0PEBU_GUID@@PEBDK1@Z`
- size: `606`
- prototype: `void *__fastcall(const unsigned __int16 *, unsigned int, const unsigned __int16 *, const struct _GUID *, const char *, unsigned int, const struct _GUID *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x140084c3c`

## callees

- `0x1400042d8`
- `0x14005613c`
- `0x140086e0c`
- `0x1400874a8`
- `0x140116f94`
- `0x140132960`
- `0x14013361c`
- `0x140133788`
- `0x1401b6a40`
- `0x1401b6bd0`
- `0x1401b7390`
- `0x1401b7528`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1401171b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1401171b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140117180`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140117180`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140117079`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140117079`

## string_xrefs

- `0x140116fdd`: `VstorCreateDeviceLogicalUnit`
- `0x14011700b`: `VhdSetUtilities::OpenStorageLogicalUnit`
- `0x140117143`: `VhdSetUtilities::OpenStorageLogicalUnit`

## pseudocode

```c

```
