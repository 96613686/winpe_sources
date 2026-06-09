# CBlbBackupAsync::AllowSourceSnapshotDeletion(_GUID,_GUID,uchar *)

- ea: `0x1400160a8`
- end: `0x1400167ee`
- name: `?AllowSourceSnapshotDeletion@CBlbBackupAsync@@AEAAJU_GUID@@0PEAE@Z`
- size: `1862`
- prototype: `int(CBlbBackupAsync *__hidden this, struct _GUID *__struct_ptr, struct _GUID *__struct_ptr, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `service_task`

## callers

- `0x140021ab0`

## callees

- `0x140006ca8`
- `0x140007ad3`
- `0x14000b25c`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140014200`
- `0x140014260`
- `0x1400142d8`
- `0x1400160a8`
- `0x14001d660`
- `0x14008bd48`
- `0x140098c04`
- `0x140098dbc`
- `0x1400f007c`
- `0x1400f07dc`
- `0x140104908`
- `0x140134cc6`
- `0x140134d20`
- `0x140137010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x14001678e`
- `ole32!CoTaskMemFree` at `0x1400167a5`
- `ole32!CoTaskMemFree` at `0x14001678e`
- `ole32!CoTaskMemFree` at `0x1400167a5`
- `RPCRT4!UuidToStringW` at `0x1400161f3`
- `RPCRT4!UuidToStringW` at `0x14001620f`
- `RPCRT4!UuidToStringW` at `0x1400161f3`
- `RPCRT4!UuidToStringW` at `0x14001620f`
- `RPCRT4!RpcStringFreeW` at `0x140016762`
- `RPCRT4!RpcStringFreeW` at `0x140016775`
- `RPCRT4!RpcStringFreeW` at `0x140016762`
- `RPCRT4!RpcStringFreeW` at `0x140016775`

## string_xrefs

- `0x140016194`: `base\stor\blb\engine\service\backup.cpp`
- `0x1400161c2`: `base\stor\blb\engine\service\backup.cpp`
- `0x1400161df`: `base\stor\blb\engine\service\backup.cpp`
- `0x14001630f`: `base\stor\blb\engine\service\backup.cpp`
- `0x140016597`: `base\stor\blb\engine\service\backup.cpp`

## pseudocode

```c

```
