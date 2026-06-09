# BioIsoStorageOpenDatabase(void *,_GUID *,ushort const *,ushort const *)

- ea: `0x1800b854c`
- end: `0x1800b85c4`
- name: `?BioIsoStorageOpenDatabase@@YAJPEAXPEAU_GUID@@PEBG2@Z`
- size: `120`
- prototype: `__int64 __fastcall(void *, struct _GUID *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18009cee0`

## callees

- `0x18005388c`
- `0x1800b854c`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800b8579`
- `RPCRT4!NdrClientCall3` at `0x1800b8579`
- `RPCRT4!RpcExceptionFilter` at `0x1800d1273`
- `RPCRT4!RpcExceptionFilter` at `0x1800d1273`

## string_xrefs

- `0x1800b85ab`: `onecore\ds\security\biometrics\service\trustlet\lib\bioisoapi.cpp`

## pseudocode

```c

```
