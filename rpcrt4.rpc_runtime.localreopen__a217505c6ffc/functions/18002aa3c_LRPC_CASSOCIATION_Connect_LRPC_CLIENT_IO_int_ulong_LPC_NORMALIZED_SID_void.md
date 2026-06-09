# LRPC_CASSOCIATION::Connect(LRPC_CLIENT_IO *,int,ulong,LPC_NORMALIZED_SID *,void *)

- ea: `0x18002aa3c`
- end: `0x18002af2c`
- name: `?Connect@LRPC_CASSOCIATION@@QEAAJPEAVLRPC_CLIENT_IO@@HKPEAVLPC_NORMALIZED_SID@@PEAX@Z`
- size: `1264`
- prototype: `__int64 __usercall@<rax>(LRPC_CASSOCIATION *__hidden this@<rcx>, struct LRPC_CLIENT_IO *@<rdx>, int@<r8d>, unsigned int@<r9d>, struct LPC_NORMALIZED_SID *, void *)`
- caller_count: `2`
- callee_count: `18`
- tags: `reparse_path, authz_impersonation, loader_planting`

## callers

- `0x180029fc0`
- `0x1800bd5b0`

## callees

- `0x180010690`
- `0x180022e80`
- `0x180023020`
- `0x180023a40`
- `0x1800295d8`
- `0x18002aa3c`
- `0x18002af34`
- `0x1800307e0`
- `0x1800315c4`
- `0x180033aa4`
- `0x180034a38`
- `0x180034dc4`
- `0x18006e1e4`
- `0x180088d9c`
- `0x18008cdd0`
- `0x180094090`
- `0x1800a5a44`
- `0x1800d7010`

## import_xrefs

- `ntdll!NtClose` at `0x18002adb6`
- `ntdll!NtClose` at `0x18002adb6`
- `ntdll!RtlLeaveCriticalSection` at `0x18002aa9b`
- `ntdll!RtlLeaveCriticalSection` at `0x18002ab70`
- `ntdll!RtlLeaveCriticalSection` at `0x18002aa9b`
- `ntdll!RtlLeaveCriticalSection` at `0x18002ab70`
- `ntdll!RtlEnterCriticalSection` at `0x18002aa76`
- `ntdll!RtlEnterCriticalSection` at `0x18002aa76`

## pseudocode

```c

```
