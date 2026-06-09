# SQLGetInfoW

- ea: `0x38386f930`
- end: `0x38386fcf6`
- name: `SQLGetInfoW`
- size: `966`
- prototype: `SQLRETURN __stdcall(SQLHDBC hdbc, SQLUSMALLINT fInfoType, SQLPOINTER rgbInfoValue, SQLSMALLINT cbInfoValueMax, SQLSMALLINT *pcbInfoValue)`
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update`

## callers

- `0x38395bb00`

## callees

- `0x3838427d0`
- `0x3838434c0`
- `0x38386a410`
- `0x38386f930`
- `0x383871610`
- `0x38387e1c0`
- `0x38389a4e0`
- `0x3838bae20`
- `0x38391ac40`
- `0x38391aed0`
- `0x38391af80`
- `0x383948b80`
- `0x38395be30`
- `0x38395c2c0`
- `0x383962350`
- `0x383a9f290`

## import_xrefs

- `MSVCR100!wcscpy_s` at `0x3838cdc8e`
- `MSVCR100!wcscpy_s` at `0x3838cdc8e`
- `MSVCR100!_wtol` at `0x3838cdd0d`
- `MSVCR100!_wtol` at `0x3838cdd0d`
- `KERNEL32!SetLastError` at `0x3838ce152`
- `KERNEL32!SetLastError` at `0x3838ce152`
- `KERNEL32!QueueUserWorkItem` at `0x3838cddd2`
- `KERNEL32!QueueUserWorkItem` at `0x3838cddd2`
- `KERNEL32!WideCharToMultiByte` at `0x3838ce19d`
- `KERNEL32!WideCharToMultiByte` at `0x3838ce19d`
- `USER32!LoadStringW` at `0x3838cdcf0`
- `USER32!LoadStringW` at `0x3838ce03d`
- `USER32!LoadStringW` at `0x3838cdcf0`
- `USER32!LoadStringW` at `0x3838ce03d`

## string_xrefs

- `0x3838cdc7f`: `SELECT CASE DATABASEPROPERTYEX( DB_NAME(), 'Updateability') WHEN 'READ_ONLY' THEN 'Y' ELSE 'N' END`

## pseudocode

```c

```
