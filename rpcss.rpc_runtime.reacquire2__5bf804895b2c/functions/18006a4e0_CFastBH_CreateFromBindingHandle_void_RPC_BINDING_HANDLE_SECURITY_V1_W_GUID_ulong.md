# CFastBH::CreateFromBindingHandle(void *,_RPC_BINDING_HANDLE_SECURITY_V1_W *,_GUID *,ulong)

- ea: `0x18006a4e0`
- end: `0x18006a7cf`
- name: `?CreateFromBindingHandle@CFastBH@@AEAAJPEAXPEAU_RPC_BINDING_HANDLE_SECURITY_V1_W@@PEAU_GUID@@K@Z`
- size: `751`
- prototype: `int(CFastBH *__hidden this, void *, struct _RPC_BINDING_HANDLE_SECURITY_V1_W *, struct _GUID *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18002d04c`

## callees

- `0x180034260`
- `0x180063dec`
- `0x18006a4e0`
- `0x180074d98`
- `0x18008172c`
- `0x180089e5c`
- `0x1800b7ac0`
- `0x1800cbffc`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x18006a789`
- `RPCRT4!RpcBindingFree` at `0x18006a7a6`
- `RPCRT4!RpcBindingFree` at `0x18006a789`
- `RPCRT4!RpcBindingFree` at `0x18006a7a6`
- `RPCRT4!RpcBindingCopy` at `0x18006a51c`
- `RPCRT4!RpcBindingCopy` at `0x18006a51c`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18006a684`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18006a684`
- `RPCRT4!RpcBindingSetObject` at `0x18006a5d8`
- `RPCRT4!RpcBindingSetObject` at `0x18006a5d8`
- `RPCRT4!RpcBindingUnbind` at `0x18006a591`
- `RPCRT4!RpcBindingUnbind` at `0x18006a743`
- `RPCRT4!RpcBindingUnbind` at `0x18006a591`
- `RPCRT4!RpcBindingUnbind` at `0x18006a743`

## string_xrefs

- `0x18006a56b`: `onecore\com\combase\common\core\fastbh.cxx`
- `0x18006a62b`: `onecore\com\combase\common\core\fastbh.cxx`
- `0x18006a564`: `CFastBH::CreateFromBindingHandle`
- `0x18006a61f`: `CFastBH::CreateFromBindingHandle`

## pseudocode

```c

```
