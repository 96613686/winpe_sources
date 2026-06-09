# SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)

- ea: `0x18002e2ac`
- end: `0x18002e40a`
- name: `?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z`
- size: `350`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, unsigned int *, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001431c`
- `0x180019bb4`
- `0x18002f358`

## callees

- `0x1800268b4`
- `0x1800269ac`
- `0x18002e2ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e361`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e361`

## string_xrefs

- `0x18002e2d3`: `SxRegReadDWORD`

## pseudocode

```c

```
