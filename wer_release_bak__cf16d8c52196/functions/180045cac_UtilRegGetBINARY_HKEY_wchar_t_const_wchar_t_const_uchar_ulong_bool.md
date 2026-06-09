# UtilRegGetBINARY(HKEY__ *,wchar_t const *,wchar_t const *,uchar *,ulong *,bool)

- ea: `0x180045cac`
- end: `0x180045d48`
- name: `?UtilRegGetBINARY@@YAJPEAUHKEY__@@PEB_W1PEAEPEAK_N@Z`
- size: `156`
- prototype: `__int64 __fastcall(HKEY, const wchar_t *, const wchar_t *, unsigned __int8 *, unsigned int *pcbData)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180006cb0`

## callees

- `0x18000716c`
- `0x180045cac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180045d1f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180045d1f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045d35`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045d35`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180045ce2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180045ce2`

## pseudocode

```c

```
