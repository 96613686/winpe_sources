# BioIsoCreateSecureBiometricUnit(_WINBIO_UNIT_SCHEMA *,ushort const *,ushort const *,ushort const *,_GUID,void * *)

- ea: `0x1800b5988`
- end: `0x1800b5aa2`
- name: `?BioIsoCreateSecureBiometricUnit@@YAJPEAU_WINBIO_UNIT_SCHEMA@@PEBG11U_GUID@@PEAPEAX@Z`
- size: `282`
- prototype: `__int64 __fastcall(struct _WINBIO_UNIT_SCHEMA *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001c2ac`

## callees

- `0x18005388c`
- `0x1800b5988`
- `0x1800b8730`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800b5a4b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800b5a4b`
- `RPCRT4!NdrClientCall3` at `0x1800b5a01`
- `RPCRT4!NdrClientCall3` at `0x1800b5a01`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800d12b7`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800d12b7`

## string_xrefs

- `0x1800b5a88`: `onecore\ds\security\biometrics\service\trustlet\lib\bioisoapi.cpp`

## pseudocode

```c

```
