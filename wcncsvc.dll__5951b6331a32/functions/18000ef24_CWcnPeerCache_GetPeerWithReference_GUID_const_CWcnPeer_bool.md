# CWcnPeerCache::GetPeerWithReference(_GUID const *,CWcnPeer * *,bool)

- ea: `0x18000ef24`
- end: `0x18000f036`
- name: `?GetPeerWithReference@CWcnPeerCache@@QEAA_NPEBU_GUID@@PEAPEAVCWcnPeer@@_N@Z`
- size: `274`
- prototype: `char __fastcall(LPCRITICAL_SECTION lpCriticalSection, const struct _GUID *, struct CWcnPeer **)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180034fd0`
- `0x180042cbc`

## callees

- `0x180004fb8`
- `0x18000ce18`
- `0x18000ef24`
- `0x1800103b8`
- `0x180053004`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000efb7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000efb7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000efed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000efed`

## pseudocode

```c

```
