# UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)

- ea: `0x1800293ac`
- end: `0x180029478`
- name: `?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z`
- size: `204`
- prototype: `unsigned int(HKEY, const wchar_t *, const wchar_t *, unsigned int, bool *, bool)`
- caller_count: `25`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180009e2c`
- `0x18000b1f4`
- `0x180017a18`
- `0x18001919c`
- `0x1800222c4`
- `0x18002e4b8`
- `0x18002f950`
- `0x1800395bc`
- `0x18003e888`
- `0x1800429c0`
- `0x18004b2c4`
- `0x1800699b0`
- `0x180081424`
- `0x1800843d0`
- `0x180089c94`
- `0x18008cf50`
- `0x18008ffa4`
- `0x1800911fc`
- `0x1800914d8`
- `0x1800982d0`
- `0x18009cd34`
- `0x1800a34d0`
- `0x1800a473c`
- `0x1800a4a9c`
- `0x1800a547c`

## callees

- `0x1800293ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002942c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002942c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029460`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029460`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800293f5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800293f5`

## pseudocode

```c

```
