# SHGetValueW

- ea: `0x180006b50`
- end: `0x180006f13`
- name: `SHGetValueW`
- size: `963`
- prototype: `LSTATUS __stdcall(HKEY hkey, LPCWSTR pszSubKey, LPCWSTR pszValue, DWORD *pdwType, void *pvData, DWORD *pcbData)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180006b50`
- `0x180007120`
- `0x180008018`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006cf6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006cf6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006bd6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006ca8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006bd6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006ca8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006c6a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006c6a`

## pseudocode

```c

```
