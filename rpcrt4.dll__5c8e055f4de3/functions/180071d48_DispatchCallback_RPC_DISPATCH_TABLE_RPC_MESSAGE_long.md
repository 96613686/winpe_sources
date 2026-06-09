# DispatchCallback(RPC_DISPATCH_TABLE *,_RPC_MESSAGE *,long *)

- ea: `0x180071d48`
- end: `0x180071e6b`
- name: `?DispatchCallback@@YAJPEAURPC_DISPATCH_TABLE@@PEAU_RPC_MESSAGE@@PEAJ@Z`
- size: `291`
- prototype: `__int64 __fastcall(struct RPC_DISPATCH_TABLE *, struct _RPC_MESSAGE *, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800716d8`
- `0x1800acadc`

## callees

- `0x1800183bc`
- `0x180071d48`
- `0x1800aa1d0`
- `0x1800d2010`

## import_xrefs

- `ntdll!DbgPrint` at `0x180071e3b`
- `ntdll!DbgPrint` at `0x180071e53`
- `ntdll!DbgPrint` at `0x180071e60`
- `ntdll!DbgPrint` at `0x180071e3b`
- `ntdll!DbgPrint` at `0x180071e53`
- `ntdll!DbgPrint` at `0x180071e60`

## string_xrefs

- `0x180071e2d`: `Possible security threat: Client is dispatching a callback`
- `0x180071e59`: `RPC: To determine the symbolic name of the callback, do an "ln" on the above address in the context of the faulting process.\n\n`

## pseudocode

```c

```
