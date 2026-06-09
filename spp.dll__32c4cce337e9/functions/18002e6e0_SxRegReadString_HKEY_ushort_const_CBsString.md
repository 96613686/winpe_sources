# SxRegReadString(HKEY__ *,ushort const *,CBsString *)

- ea: `0x18002e6e0`
- end: `0x18002e87a`
- name: `?SxRegReadString@@YAJPEAUHKEY__@@PEBGPEAVCBsString@@@Z`
- size: `410`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, struct CBsString *this)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180010c18`
- `0x180018f10`
- `0x180019bb4`
- `0x18002d00c`
- `0x18002d8f4`

## callees

- `0x1800268b4`
- `0x1800269ac`
- `0x18002e6e0`
- `0x180034ed4`
- `0x180034fe4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e7a3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e7a3`

## string_xrefs

- `0x18002e6fc`: `SxRegReadString`

## pseudocode

```c

```
