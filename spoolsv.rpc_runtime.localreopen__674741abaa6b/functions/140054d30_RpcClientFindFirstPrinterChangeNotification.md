# RpcClientFindFirstPrinterChangeNotification

- ea: `0x140054d30`
- end: `0x140054e7d`
- name: `RpcClientFindFirstPrinterChangeNotification`
- size: `333`
- prototype: `__int64 __fastcall(struct _PRINTHANDLE *, unsigned int, unsigned int, DWORD dwProcessId, struct _PRINTER_NOTIFY_OPTIONS *, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x1400028e0`
- `0x140002940`
- `0x140003d60`
- `0x14001748c`
- `0x140054c04`
- `0x140054d30`
- `0x14006cc88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140054e65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140054e65`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140054dd2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140054dd2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140054d7c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140054e51`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140054d7c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x140054e51`
- `RPCRT4!RpcServerInqBindingHandle` at `0x140054d5d`
- `RPCRT4!RpcServerInqBindingHandle` at `0x140054d5d`

## string_xrefs

- `0x140054d9e`: `Rpc call is access denied.`

## pseudocode

```c

```
