# GetMachineAccountSidWorker(LRPC_CLIENT_IO *)

- ea: `0x1800c13b0`
- end: `0x1800c144f`
- name: `?GetMachineAccountSidWorker@@YAXPEAVLRPC_CLIENT_IO@@@Z`
- size: `159`
- prototype: `void __fastcall(struct LRPC_CLIENT_IO *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800295d8`
- `0x180031908`
- `0x180032f20`
- `0x180036464`
- `0x1800c12f0`
- `0x1800c13b0`

## import_xrefs

- `ntdll!RtlRunOnceBeginInitialize` at `0x1800c1402`
- `ntdll!RtlRunOnceBeginInitialize` at `0x1800c1402`
- `ntdll!RtlEnterCriticalSection` at `0x1800c1415`
- `ntdll!RtlEnterCriticalSection` at `0x1800c1415`

## pseudocode

```c

```
