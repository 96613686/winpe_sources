# SettingsCopier::SetRegKeyValue(HKEY__ *,ushort const *,ushort const *,ulong,uchar const *,ulong)

- ea: `0x180387c00`
- end: `0x180387d63`
- name: `?SetRegKeyValue@SettingsCopier@@CAJPEAUHKEY__@@PEBG1KPEBEK@Z`
- size: `355`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, LPCWSTR lpValueName, DWORD dwType, BYTE *lpData, DWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, registry_config`

## callers

- `0x1803870ac`

## callees

- `0x180387c00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180387ce0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180387ce0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180387d40`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180387d40`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180387c70`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180387c70`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180387c91`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180387cf5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180387d16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180387d4c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180387c91`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180387cf5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180387d16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180387d4c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180387cb2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180387cb2`

## string_xrefs

- `0x180387cd9`: `SymbolicLinkValue`

## pseudocode

```c

```
