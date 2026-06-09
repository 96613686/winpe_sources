# GetClientIdentifier(ushort *,ulong)

- ea: `0x1800852d8`
- end: `0x1800855f9`
- name: `?GetClientIdentifier@@YAJPEAGK@Z`
- size: `801`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800858d4`

## callees

- `0x180003383`
- `0x1800044bf`
- `0x18000b1d8`
- `0x18000ec94`
- `0x18000ece0`
- `0x180010ba4`
- `0x18001b7e4`
- `0x1800852d8`
- `0x18009a520`

## import_xrefs

- `msvcrt!_wcslwr_s` at `0x180085576`
- `msvcrt!_wcslwr_s` at `0x180085576`
- `msvcrt!wcsrchr` at `0x1800854ab`
- `msvcrt!wcsrchr` at `0x180085523`
- `msvcrt!wcsrchr` at `0x1800854ab`
- `msvcrt!wcsrchr` at `0x180085523`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180085378`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180085378`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085382`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800853f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085382`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800853f5`

## string_xrefs

- `0x180085557`: `pszExtension`
- `0x18008540e`: `com.microsoft.rdc.windows.%s.x64`

## pseudocode

```c

```
