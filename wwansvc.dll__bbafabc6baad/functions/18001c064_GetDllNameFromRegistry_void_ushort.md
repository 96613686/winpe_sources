# GetDllNameFromRegistry(void *,ushort *)

- ea: `0x18001c064`
- end: `0x18001c159`
- name: `?GetDllNameFromRegistry@@YAKPEAXPEAG@Z`
- size: `245`
- prototype: `unsigned int __fastcall(HKEY hKey, LPWSTR lpDst)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001bf28`

## callees

- `0x1800085d0`
- `0x180012300`
- `0x18001c064`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c0eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c0eb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001c0df`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001c0df`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001c130`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001c130`

## string_xrefs

- `0x18001c0c8`: `DimDLL`
- `0x18001c0f1`: `Error %d getting DLL name from registry`
- `0x18001c0fd`: `GetDllNameFromRegistry`
- `0x18001c112`: `GetDllNameFromRegistry`
- `0x18001c109`: `GetDllNameFromRegistry failed.`

## pseudocode

```c

```
