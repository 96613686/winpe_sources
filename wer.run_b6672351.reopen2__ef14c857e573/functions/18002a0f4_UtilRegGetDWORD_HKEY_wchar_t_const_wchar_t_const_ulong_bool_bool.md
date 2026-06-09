# UtilRegGetDWORD(HKEY__ *,wchar_t const *,wchar_t const *,ulong,bool *,bool)

- ea: `0x18002a0f4`
- end: `0x18002a1d3`
- name: `?UtilRegGetDWORD@@YAKPEAUHKEY__@@PEB_W1KPEA_N_N@Z`
- size: `223`
- prototype: `unsigned int(HKEY, const wchar_t *, const wchar_t *, unsigned int, bool *, bool)`
- caller_count: `29`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000aed8`
- `0x18000c504`
- `0x180013838`
- `0x18001c38c`
- `0x180022e44`
- `0x180026b60`
- `0x180030058`
- `0x180031310`
- `0x180037164`
- `0x18004083c`
- `0x180044080`
- `0x180047140`
- `0x1800494a8`
- `0x18004d530`
- `0x18004df60`
- `0x18006cb20`
- `0x180084fdc`
- `0x18008808c`
- `0x18008db14`
- `0x180090ec0`
- `0x18009407c`
- `0x1800952e4`
- `0x1800955c0`
- `0x18009c6fc`
- `0x1800a168c`
- `0x1800a8108`
- `0x1800a9464`
- `0x1800a9878`
- `0x1800aa2c8`

## callees

- `0x18002a0f4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a17a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002a17a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a1b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a1b4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a13d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a13d`

## pseudocode

```c

```
