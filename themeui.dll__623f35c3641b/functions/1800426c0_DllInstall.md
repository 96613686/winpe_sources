# DllInstall

- ea: `0x1800426c0`
- end: `0x1800427d4`
- name: `DllInstall`
- size: `276`
- prototype: `HRESULT __stdcall(BOOL bInstall, PCWSTR pszCmdLine)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800415cc`
- `0x180041a2c`
- `0x1800426c0`
- `0x18004283c`

## import_xrefs

- `SHLWAPI!StrStrW` at `0x1800426df`
- `SHLWAPI!StrStrW` at `0x180042700`
- `SHLWAPI!StrStrW` at `0x1800426df`
- `SHLWAPI!StrStrW` at `0x180042700`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18004272d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18004272d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180042760`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180042760`
- `ext-ms-win-com-sta-l1-1-0!CoInitialize` at `0x18004274a`
- `ext-ms-win-com-sta-l1-1-0!CoInitialize` at `0x18004274a`

## string_xrefs

- `0x1800426f6`: `/InstallVS:'`
- `0x1800426d5`: `/UserInstall`

## pseudocode

```c

```
