# UtilRegGetBINARY(HKEY__ *,wchar_t const *,wchar_t const *,uchar *,ulong *,bool)

- ea: `0x180047c0c`
- end: `0x180047cbb`
- name: `?UtilRegGetBINARY@@YAJPEAUHKEY__@@PEB_W1PEAEPEAK_N@Z`
- size: `175`
- prototype: `int(HKEY, const wchar_t *, const wchar_t *, unsigned __int8 *, unsigned int *, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001be50`

## callees

- `0x18001c368`
- `0x180047c0c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180047c85`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180047c85`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180047ca1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180047ca1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180047c42`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180047c42`

## pseudocode

```c

```
