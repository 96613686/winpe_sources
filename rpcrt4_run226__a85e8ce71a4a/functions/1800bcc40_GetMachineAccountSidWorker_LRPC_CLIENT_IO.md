# GetMachineAccountSidWorker(LRPC_CLIENT_IO *)

- ea: `0x1800bcc40`
- end: `0x1800bccd2`
- name: `?GetMachineAccountSidWorker@@YAXPEAVLRPC_CLIENT_IO@@@Z`
- size: `146`
- prototype: `void __fastcall(struct LRPC_CLIENT_IO *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800283bc`
- `0x180030578`
- `0x180031ae4`
- `0x180063a8c`
- `0x1800bcb84`
- `0x1800bcc40`

## import_xrefs

- `ntdll!RtlRunOnceBeginInitialize` at `0x1800bcc92`
- `ntdll!RtlRunOnceBeginInitialize` at `0x1800bcc92`
- `ntdll!RtlEnterCriticalSection` at `0x1800bcc9f`
- `ntdll!RtlEnterCriticalSection` at `0x1800bcc9f`

## pseudocode

```c

```
