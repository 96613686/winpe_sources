# AUTOPROXY_RPC_SERVER::GetProxySettingsEx(_RPC_ASYNC_STATE *,void *,_SESSION_OPTIONS const *,ulong,unsigned __int64,ushort const *,ushort const *,_PROXY_SETTINGS_EX *)

- ea: `0x1800accd8`
- end: `0x1800ad190`
- name: `?GetProxySettingsEx@AUTOPROXY_RPC_SERVER@@AEAAJPEAU_RPC_ASYNC_STATE@@PEAXPEBU_SESSION_OPTIONS@@K_KPEBG4PEAU_PROXY_SETTINGS_EX@@@Z`
- size: `1208`
- prototype: `int(AUTOPROXY_RPC_SERVER *__hidden this, struct _RPC_ASYNC_STATE *, void *, const struct _SESSION_OPTIONS *, unsigned int, unsigned __int64, const unsigned __int16 *, const unsigned __int16 *, struct _PROXY_SETTINGS_EX *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800addf0`

## callees

- `0x18000eb88`
- `0x180019384`
- `0x1800193a0`
- `0x18001f4b8`
- `0x1800403d4`
- `0x180069620`
- `0x180069c70`
- `0x180070048`
- `0x1800743f0`
- `0x1800a0d24`
- `0x1800a1d10`
- `0x1800a2660`
- `0x1800accd8`
- `0x1800c7d08`
- `0x1800d2e4c`
- `0x1800db6b0`
- `0x1800de010`

## import_xrefs

- `RPCRT4!RpcAsyncAbortCall` at `0x1800ace1c`
- `RPCRT4!RpcAsyncAbortCall` at `0x1800ace1c`
- `RPCRT4!RpcRaiseException` at `0x1800ace50`
- `RPCRT4!RpcRaiseException` at `0x1800ad189`
- `RPCRT4!RpcRaiseException` at `0x1800ace50`
- `RPCRT4!RpcRaiseException` at `0x1800ad189`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800ad155`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800ad155`

## pseudocode

```c

```
