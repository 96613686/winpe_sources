# Registry::GetDWORDStr(ushort const *,ulong *)

- ea: `0x18000f380`
- end: `0x18000f4b1`
- name: `?GetDWORDStr@Registry@@QEAAHPEBGPEAK@Z`
- size: `305`
- prototype: `__int64 __fastcall(Registry *__hidden this, const unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000f2b8`
- `0x180041970`

## callees

- `0x18000f380`
- `0x1800101cc`
- `0x18002ed08`
- `0x180044310`
- `0x180047010`

## import_xrefs

- `msvcrt!wcstoul` at `0x18000f435`
- `msvcrt!wcstoul` at `0x18000f435`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f4a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f4a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f48a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f48a`

## pseudocode

```c

```
