# OSF_CCONNECTION::FinishSecurityContextSetup(OSF_CCALL *,rpcconn_common * *,uint *,int *,ulong)

- ea: `0x18006a45c`
- end: `0x18006a7b7`
- name: `?FinishSecurityContextSetup@OSF_CCONNECTION@@QEAAJPEAVOSF_CCALL@@PEAPEAUrpcconn_common@@PEAIPEAHK@Z`
- size: `859`
- prototype: `__int64 __fastcall(OSF_CCONNECTION *__hidden this, struct OSF_CCALL *, struct rpcconn_common **, unsigned int *, int *, unsigned int)`
- caller_count: `2`
- callee_count: `16`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18005f404`
- `0x1800b03a8`

## callees

- `0x18000fd70`
- `0x180012f68`
- `0x180023020`
- `0x180026500`
- `0x18005bed4`
- `0x18005c538`
- `0x18005feb0`
- `0x180069090`
- `0x18006a050`
- `0x18006a45c`
- `0x18006a9c0`
- `0x18006c668`
- `0x1800936d8`
- `0x18009392c`
- `0x1800970ac`
- `0x1800b15f8`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18006a716`
- `ntdll!RtlLeaveCriticalSection` at `0x18006a716`
- `ntdll!RtlEnterCriticalSection` at `0x18006a6b9`
- `ntdll!RtlEnterCriticalSection` at `0x18006a6b9`

## pseudocode

```c

```
