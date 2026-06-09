# RpcAddPrinterDriverEx

- ea: `0x140034d10`
- end: `0x140034ebc`
- name: `RpcAddPrinterDriverEx`
- size: `428`
- prototype: `DWORD __fastcall(WCHAR *, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `15`
- tags: `installer_update`

## callees

- `0x1400028e0`
- `0x140002940`
- `0x140003d60`
- `0x140017328`
- `0x1400173c0`
- `0x14001748c`
- `0x140017538`
- `0x14001755c`
- `0x1400325b8`
- `0x1400329b8`
- `0x140034d10`
- `0x14003ad10`
- `0x14003d3c4`
- `0x14003d53c`
- `0x14005e898`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140034df8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140034df8`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140034d9e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140034e96`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140034d9e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140034e96`
- `RPCRT4!RpcServerInqBindingHandle` at `0x140034d7f`
- `RPCRT4!RpcServerInqBindingHandle` at `0x140034d7f`

## string_xrefs

- `0x140034dc0`: `Rpc call is access denied.`
- `0x140034e5e`: `RestrictDriverInstallationToAdministrators is set and the user is not an Administrator. Returning ACCESS DENIED.`

## pseudocode

```c

```
