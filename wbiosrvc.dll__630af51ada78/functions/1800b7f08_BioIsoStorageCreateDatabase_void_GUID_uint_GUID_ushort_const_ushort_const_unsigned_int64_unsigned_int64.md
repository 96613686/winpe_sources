# BioIsoStorageCreateDatabase(void *,_GUID *,uint,_GUID *,ushort const *,ushort const *,unsigned __int64,unsigned __int64)

- ea: `0x1800b7f08`
- end: `0x1800b7faf`
- name: `?BioIsoStorageCreateDatabase@@YAJPEAXPEAU_GUID@@I1PEBG2_K3@Z`
- size: `167`
- prototype: `__int64 __fastcall(void *, struct _GUID *, unsigned int, struct _GUID *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18009cc60`

## callees

- `0x18005388c`
- `0x1800b7f08`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800b7f64`
- `RPCRT4!NdrClientCall3` at `0x1800b7f64`
- `RPCRT4!RpcExceptionFilter` at `0x1800d136b`
- `RPCRT4!RpcExceptionFilter` at `0x1800d136b`

## string_xrefs

- `0x1800b7f96`: `onecore\ds\security\biometrics\service\trustlet\lib\bioisoapi.cpp`

## pseudocode

```c

```
