# ReadRegistryString

- ea: `0x180049cb0`
- end: `0x180049ed3`
- name: `ReadRegistryString`
- size: `547`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, SIZE_T dwBytes, LPWSTR lpDst)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18004960c`
- `0x180049f3c`

## callees

- `0x1800053c0`
- `0x1800063a0`
- `0x180006934`
- `0x18003af80`
- `0x180049cb0`
- `0x180049edc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049e3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049e3f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180049d94`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180049d94`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180049e21`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180049e21`

## pseudocode

```c

```
