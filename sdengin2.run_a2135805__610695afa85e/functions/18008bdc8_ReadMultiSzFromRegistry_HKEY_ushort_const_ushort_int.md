# ReadMultiSzFromRegistry(HKEY__ *,ushort const *,ushort * *,int)

- ea: `0x18008bdc8`
- end: `0x18008c038`
- name: `?ReadMultiSzFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAGH@Z`
- size: `624`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, unsigned __int16 **, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18008bc8c`

## callees

- `0x180009d0c`
- `0x180072e08`
- `0x180072f14`
- `0x18008bdc8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008be63`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008bf39`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008be63`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008bf39`
- `ole32!CoTaskMemAlloc` at `0x18008beef`
- `ole32!CoTaskMemAlloc` at `0x18008beef`

## string_xrefs

- `0x18008bde9`: `ReadMultiSzFromRegistry`

## pseudocode

```c

```
