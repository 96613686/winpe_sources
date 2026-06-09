# BioIsoPresenceMonitorGetChanges(void *,void * *,_WINBIO_PRESENCE * *,unsigned __int64 *,_WINBIO_PRESENCE * *,unsigned __int64 *,_WINBIO_PRESENCE * *,unsigned __int64 *,_WINBIO_PRESENCE * *,unsigned __int64 *)

- ea: `0x1800b6f14`
- end: `0x1800b7051`
- name: `?BioIsoPresenceMonitorGetChanges@@YAJPEAXPEAPEAXPEAPEAU_WINBIO_PRESENCE@@PEA_K232323@Z`
- size: `317`
- prototype: `__int64 __fastcall(void *, void **, struct _WINBIO_PRESENCE **, unsigned __int64 *, struct _WINBIO_PRESENCE **, unsigned __int64 *, struct _WINBIO_PRESENCE **, unsigned __int64 *, struct _WINBIO_PRESENCE **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005f620`

## callees

- `0x18005388c`
- `0x1800b6f14`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800b6faf`
- `RPCRT4!NdrClientCall3` at `0x1800b6faf`
- `RPCRT4!RpcExceptionFilter` at `0x1800d138d`
- `RPCRT4!RpcExceptionFilter` at `0x1800d138d`

## string_xrefs

- `0x1800b6ff5`: `onecore\ds\security\biometrics\service\trustlet\lib\bioisoapi.cpp`

## pseudocode

```c

```
