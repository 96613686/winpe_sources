# _readMultiSzVal

- ea: `0x1800a3b34`
- end: `0x1800a3c8d`
- name: `_readMultiSzVal`
- size: `345`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpValueName@<rdx>, DWORD cbData, int)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18009c0a0`
- `0x1800a36f4`
- `0x1800a39b4`
- `0x1800a3c94`

## callees

- `0x180012300`
- `0x180016c50`
- `0x180074758`
- `0x180074cec`
- `0x1800a3b34`
- `0x1800b6a40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3c04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a3c04`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a3b93`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a3c38`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a3b93`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a3c38`

## string_xrefs

- `0x1800a3b44`: `_readMultiSzVal`

## pseudocode

```c

```
