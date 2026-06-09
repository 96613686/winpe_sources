# HcsGetServiceProperties

- ea: `0x180026640`
- end: `0x180026877`
- name: `HcsGetServiceProperties`
- size: `567`
- prototype: `HRESULT __stdcall(PCWSTR propertyQuery, PWSTR *result)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002b900`

## callees

- `0x180002f50`
- `0x180003c78`
- `0x18000d108`
- `0x180017014`
- `0x1800170e4`
- `0x180018744`
- `0x180020a94`
- `0x180021170`
- `0x18002492c`
- `0x180026640`
- `0x180049ac4`
- `0x180086010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026753`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026769`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002680e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026753`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026769`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002680e`

## string_xrefs

- `0x180026858`: `onecore\vm\compute\dll\legacy\src\computeservice.cpp`
- `0x18002669f`: `HcsGetServiceProperties_v1`

## pseudocode

```c

```
