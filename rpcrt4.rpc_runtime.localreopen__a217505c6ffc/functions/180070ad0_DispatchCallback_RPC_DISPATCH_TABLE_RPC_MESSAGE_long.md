# DispatchCallback(RPC_DISPATCH_TABLE *,_RPC_MESSAGE *,long *)

- ea: `0x180070ad0`
- end: `0x180070c06`
- name: `?DispatchCallback@@YAJPEAURPC_DISPATCH_TABLE@@PEAU_RPC_MESSAGE@@PEAJ@Z`
- size: `310`
- prototype: `__int64 __fastcall(struct RPC_DISPATCH_TABLE *, struct _RPC_MESSAGE *, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180070458`
- `0x1800b0600`

## callees

- `0x1800167d8`
- `0x180070ad0`
- `0x1800adb74`
- `0x1800d7010`

## import_xrefs

- `ntdll!DbgPrint` at `0x180070bc4`
- `ntdll!DbgPrint` at `0x180070be2`
- `ntdll!DbgPrint` at `0x180070bf5`
- `ntdll!DbgPrint` at `0x180070bc4`
- `ntdll!DbgPrint` at `0x180070be2`
- `ntdll!DbgPrint` at `0x180070bf5`

## string_xrefs

- `0x180070bb6`: `Possible security threat: Client is dispatching a callback`
- `0x180070bee`: `RPC: To determine the symbolic name of the callback, do an "ln" on the above address in the context of the faulting process.\n\n`

## pseudocode

```c

```
