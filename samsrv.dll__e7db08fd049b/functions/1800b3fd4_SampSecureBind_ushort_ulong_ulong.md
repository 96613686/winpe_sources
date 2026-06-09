# SampSecureBind(ushort *,ulong,ulong)

- ea: `0x1800b3fd4`
- end: `0x1800b40da`
- name: `?SampSecureBind@@YAPEAXPEAGKK@Z`
- size: `262`
- prototype: `void *__fastcall(unsigned __int16 *, unsigned int AuthnLevel, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18009b894`
- `0x18009f64c`
- `0x1800a1370`

## callees

- `0x1800b3c38`
- `0x1800b3fd4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b40a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b40a9`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800b4034`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800b4034`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800b401b`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800b401b`
- `RPCRT4!RpcBindingFree` at `0x1800b40c3`
- `RPCRT4!RpcBindingFree` at `0x1800b40c3`
- `RPCRT4!RpcStringFreeW` at `0x1800b4041`
- `RPCRT4!RpcStringFreeW` at `0x1800b4041`
- `RPCRT4!RpcBindingSetAuthInfoW` at `0x1800b409d`
- `RPCRT4!RpcBindingSetAuthInfoW` at `0x1800b409d`

## pseudocode

```c

```
