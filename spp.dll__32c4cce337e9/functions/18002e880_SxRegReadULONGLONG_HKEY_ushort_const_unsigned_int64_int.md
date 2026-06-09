# SxRegReadULONGLONG(HKEY__ *,ushort const *,unsigned __int64 *,int)

- ea: `0x18002e880`
- end: `0x18002e9b1`
- name: `?SxRegReadULONGLONG@@YAJPEAUHKEY__@@PEBGPEA_KH@Z`
- size: `305`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, unsigned __int64 *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001be74`
- `0x18001d97c`

## callees

- `0x1800268b4`
- `0x1800269ac`
- `0x18002e880`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e92c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e92c`

## string_xrefs

- `0x18002e8a3`: `SxRegReadULONGLONG`

## pseudocode

```c

```
