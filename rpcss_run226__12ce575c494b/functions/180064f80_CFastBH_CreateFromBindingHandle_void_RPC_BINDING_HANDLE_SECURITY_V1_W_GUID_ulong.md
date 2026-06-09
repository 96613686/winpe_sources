# CFastBH::CreateFromBindingHandle(void *,_RPC_BINDING_HANDLE_SECURITY_V1_W *,_GUID *,ulong)

- ea: `0x180064f80`
- end: `0x180065238`
- name: `?CreateFromBindingHandle@CFastBH@@AEAAJPEAXPEAU_RPC_BINDING_HANDLE_SECURITY_V1_W@@PEAU_GUID@@K@Z`
- size: `696`
- prototype: `int(CFastBH *__hidden this, void *, struct _RPC_BINDING_HANDLE_SECURITY_V1_W *, struct _GUID *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180022e54`

## callees

- `0x1800315fc`
- `0x180034540`
- `0x180064f80`
- `0x180070740`
- `0x18007e3d4`
- `0x180085140`
- `0x1800b27e0`
- `0x1800c6074`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x1800651ff`
- `RPCRT4!RpcBindingFree` at `0x180065216`
- `RPCRT4!RpcBindingFree` at `0x1800651ff`
- `RPCRT4!RpcBindingFree` at `0x180065216`
- `RPCRT4!RpcBindingCopy` at `0x180064fbc`
- `RPCRT4!RpcBindingCopy` at `0x180064fbc`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180065106`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180065106`
- `RPCRT4!RpcBindingSetObject` at `0x180065068`
- `RPCRT4!RpcBindingSetObject` at `0x180065068`
- `RPCRT4!RpcBindingUnbind` at `0x18006502b`
- `RPCRT4!RpcBindingUnbind` at `0x1800651bf`
- `RPCRT4!RpcBindingUnbind` at `0x18006502b`
- `RPCRT4!RpcBindingUnbind` at `0x1800651bf`

## string_xrefs

- `0x180065005`: `onecore\com\combase\common\core\fastbh.cxx`
- `0x1800650ad`: `onecore\com\combase\common\core\fastbh.cxx`
- `0x180064ffe`: `CFastBH::CreateFromBindingHandle`
- `0x1800650a1`: `CFastBH::CreateFromBindingHandle`

## pseudocode

```c

```
