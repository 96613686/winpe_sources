# CWcnPeerCache::WalkListOfPeers(void (*)(void *,_GUID const *,CWcnPeer *),void *,bool)

- ea: `0x18000fab8`
- end: `0x18000fc02`
- name: `?WalkListOfPeers@CWcnPeerCache@@QEAAXP6AXPEAXPEBU_GUID@@PEAVCWcnPeer@@@Z0_N@Z`
- size: `330`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, void (*)(void *, const struct _GUID *, struct CWcnPeer *), void *, bool)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180034ec0`
- `0x1800351b0`
- `0x18003e6c0`
- `0x18004677c`

## callees

- `0x180004fb8`
- `0x18000fab8`
- `0x180053004`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fb10`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000fb10`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fbbc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fbbc`

## pseudocode

```c

```
