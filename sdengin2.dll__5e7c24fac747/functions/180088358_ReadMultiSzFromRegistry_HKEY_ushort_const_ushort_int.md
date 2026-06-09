# ReadMultiSzFromRegistry(HKEY__ *,ushort const *,ushort * *,int)

- ea: `0x180088358`
- end: `0x1800885b5`
- name: `?ReadMultiSzFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAGH@Z`
- size: `605`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, unsigned __int16 **, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180088228`

## callees

- `0x180009a98`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180088358`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800883f3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800884bd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800883f3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800884bd`
- `ole32!CoTaskMemAlloc` at `0x180088479`
- `ole32!CoTaskMemAlloc` at `0x180088479`

## string_xrefs

- `0x180088379`: `ReadMultiSzFromRegistry`

## pseudocode

```c

```
