# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180018328`
- end: `0x1800184c3`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `411`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PVOID Ptr, struct IUnknown **)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180018150`
- `0x1800273d4`

## callees

- `0x180018328`
- `0x180029210`
- `0x18002a508`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800183c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800183c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018450`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018450`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180018378`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180018378`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180018396`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180018497`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180018396`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180018497`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180018436`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180018436`

## pseudocode

```c

```
