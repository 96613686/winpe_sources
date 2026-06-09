# RpcClientFindFirstPrinterChangeNotification

- ea: `0x140050070`
- end: `0x140050197`
- name: `RpcClientFindFirstPrinterChangeNotification`
- size: `295`
- prototype: `__int64 __fastcall(struct _PRINTHANDLE *, unsigned int, unsigned int, DWORD dwProcessId, struct _PRINTER_NOTIFY_OPTIONS *, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x140002a70`
- `0x140002ac0`
- `0x1400037d0`
- `0x1400160a0`
- `0x14004ff54`
- `0x140050070`
- `0x14006669c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140050186`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140050186`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140050106`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140050106`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400500b6`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14005017c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1400500b6`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x14005017c`
- `RPCRT4!RpcServerInqBindingHandle` at `0x14005009d`
- `RPCRT4!RpcServerInqBindingHandle` at `0x14005009d`

## string_xrefs

- `0x1400500d2`: `Rpc call is access denied.`

## pseudocode

```c

```
