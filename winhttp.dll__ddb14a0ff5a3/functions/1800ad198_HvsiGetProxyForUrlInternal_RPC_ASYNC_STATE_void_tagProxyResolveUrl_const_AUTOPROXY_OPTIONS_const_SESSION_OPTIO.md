# HvsiGetProxyForUrlInternal(_RPC_ASYNC_STATE *,void *,tagProxyResolveUrl const *,_AUTOPROXY_OPTIONS const *,_SESSION_OPTIONS const *,ulong,uchar *,_PROXY_RESULT *,void * *)

- ea: `0x1800ad198`
- end: `0x1800ad40f`
- name: `?HvsiGetProxyForUrlInternal@@YAXPEAU_RPC_ASYNC_STATE@@PEAXPEBUtagProxyResolveUrl@@PEBU_AUTOPROXY_OPTIONS@@PEBU_SESSION_OPTIONS@@KPEAEPEAU_PROXY_RESULT@@PEAPEAX@Z`
- size: `631`
- prototype: `void __fastcall(struct _RPC_ASYNC_STATE *, void *, const struct tagProxyResolveUrl *, const struct _AUTOPROXY_OPTIONS *, const struct _SESSION_OPTIONS *, unsigned int, unsigned __int8 *, struct _PROXY_RESULT *, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180069920`

## callees

- `0x180003eec`
- `0x1800707ec`
- `0x18008bfc4`
- `0x180091f14`
- `0x180097bf0`
- `0x1800a1d10`
- `0x1800ad198`
- `0x1800c8f7c`
- `0x1800d2190`
- `0x1800d2cb8`
- `0x1800db6b0`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ad221`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ad3d3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ad221`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ad3d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ad360`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ad360`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800ad377`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800ad377`

## pseudocode

```c

```
