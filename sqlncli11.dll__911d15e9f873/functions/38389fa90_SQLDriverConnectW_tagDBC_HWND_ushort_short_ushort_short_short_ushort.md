# SQLDriverConnectW(tagDBC *,HWND__ *,ushort *,short,ushort *,short,short *,ushort)

- ea: `0x38389fa90`
- end: `0x38389fedf`
- name: `?SQLDriverConnectW@@YAFPEAUtagDBC@@PEAUHWND__@@PEAGF2FPEAFG@Z`
- size: `1103`
- prototype: `SQLRETURN __stdcall(SQLHDBC hdbc, SQLHWND hwnd, SQLWCHAR *szConnStrIn, SQLSMALLINT cchConnStrIn, SQLWCHAR *szConnStrOut, SQLSMALLINT cchConnStrOutMax, SQLSMALLINT *pcchConnStrOut, SQLUSMALLINT fDriverCompletion)`
- caller_count: `0`
- callee_count: `22`
- tags: `broker_com_uri`

## callees

- `0x3838434c0`
- `0x38386a410`
- `0x38386d3f4`
- `0x38387c820`
- `0x38387c938`
- `0x38389a4e0`
- `0x38389d110`
- `0x38389d160`
- `0x38389da10`
- `0x38389e7c0`
- `0x38389fa90`
- `0x38389fef0`
- `0x3838a07e0`
- `0x3838a1b80`
- `0x3838ba520`
- `0x3838ba870`
- `0x38391ac40`
- `0x38391aed0`
- `0x38391af80`
- `0x3839203c0`
- `0x383920d10`
- `0x383a9f290`

## import_xrefs

- `MSVCR100!_wcsicmp` at `0x3838c2d44`
- `MSVCR100!_wcsicmp` at `0x3838c2d44`
- `USER32!DialogBoxParamW` at `0x3838c300e`
- `USER32!DialogBoxParamW` at `0x3838c300e`
- `USER32!GetDesktopWindow` at `0x3838c2fe1`
- `USER32!GetDesktopWindow` at `0x3838c2fe1`

## pseudocode

```c

```
