# AddPrinterDriverExW

- ea: `0x1400649c0`
- end: `0x140064b04`
- name: `AddPrinterDriverExW`
- size: `324`
- prototype: `BOOL __stdcall(LPWSTR pName, DWORD Level, PBYTE lpbDriverInfo, DWORD dwFileCopyFlags)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x14003ad10`

## callees

- `0x14000e700`
- `0x140015378`
- `0x140017b40`
- `0x140018f1c`
- `0x14005e6f8`
- `0x1400649c0`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140064a24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140064a72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140064a91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140064ad4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140064a24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140064a72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140064a91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140064ad4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140064a0a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140064abf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140064a0a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140064abf`

## string_xrefs

- `0x1400649f2`: `Trying to install printer driver %ws but installation of printer drivers is not allowed in ContainerOS`

## pseudocode

```c

```
