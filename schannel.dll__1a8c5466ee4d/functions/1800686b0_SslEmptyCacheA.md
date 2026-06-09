# SslEmptyCacheA

- ea: `0x1800686b0`
- end: `0x180068730`
- name: `SslEmptyCacheA`
- size: `128`
- prototype: `BOOL __stdcall(LPSTR pszTargetName, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800686b0`
- `0x180068740`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800686fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800686fd`
- `ntdll!RtlFreeUnicodeString` at `0x180068722`
- `ntdll!RtlFreeUnicodeString` at `0x180068722`
- `ntdll!RtlInitAnsiString` at `0x1800686db`
- `ntdll!RtlInitAnsiString` at `0x1800686db`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800686ee`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x1800686ee`

## pseudocode

```c

```
