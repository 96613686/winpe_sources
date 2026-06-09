# SslEmptyCacheW

- ea: `0x180068740`
- end: `0x1800688b7`
- name: `SslEmptyCacheW`
- size: `375`
- prototype: `BOOL __stdcall(LPWSTR pszTargetName, DWORD dwFlags)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800686b0`

## callees

- `0x180014240`
- `0x180021eb0`
- `0x180068740`
- `0x180088a54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006888f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006888f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800687dd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800687dd`
- `ntdll!RtlInitAnsiString` at `0x180068794`
- `ntdll!RtlInitAnsiString` at `0x180068794`
- `SspiCli!LsaCallAuthenticationPackage` at `0x180068859`
- `SspiCli!LsaCallAuthenticationPackage` at `0x180068859`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1800687a6`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1800687a6`
- `SspiCli!LsaConnectUntrusted` at `0x180068779`
- `SspiCli!LsaConnectUntrusted` at `0x180068779`
- `SspiCli!LsaDeregisterLogonProcess` at `0x180068876`
- `SspiCli!LsaDeregisterLogonProcess` at `0x180068876`

## pseudocode

```c

```
