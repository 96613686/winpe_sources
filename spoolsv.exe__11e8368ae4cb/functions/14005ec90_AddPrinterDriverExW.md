# AddPrinterDriverExW

- ea: `0x14005ec90`
- end: `0x14005edaf`
- name: `AddPrinterDriverExW`
- size: `287`
- prototype: `BOOL __stdcall(LPWSTR pName, DWORD Level, PBYTE lpbDriverInfo, DWORD dwFileCopyFlags)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x140037c30`

## callees

- `0x14000d520`
- `0x1400140cc`
- `0x1400166e8`
- `0x140017a54`
- `0x140058f60`
- `0x14005ec90`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005ecee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005ed36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005ed4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005ed86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005ecee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005ed36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005ed4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005ed86`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005ecda`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005ed77`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005ecda`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005ed77`

## string_xrefs

- `0x14005ecc2`: `Trying to install printer driver %ws but installation of printer drivers is not allowed in ContainerOS`

## pseudocode

```c

```
