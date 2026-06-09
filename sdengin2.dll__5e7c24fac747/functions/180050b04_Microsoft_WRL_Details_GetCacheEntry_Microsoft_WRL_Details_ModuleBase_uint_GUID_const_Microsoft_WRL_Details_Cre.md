# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180050b04`
- end: `0x180050c8b`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PSRWLOCK SRWLock, struct IUnknown **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18004e204`

## callees

- `0x180050b04`
- `0x180051434`
- `0x1800cb010`

## import_xrefs

- `KERNEL32!EncodePointer` at `0x180050c0e`
- `KERNEL32!EncodePointer` at `0x180050c0e`
- `KERNEL32!DecodePointer` at `0x180050b68`
- `KERNEL32!DecodePointer` at `0x180050c1d`
- `KERNEL32!DecodePointer` at `0x180050b68`
- `KERNEL32!DecodePointer` at `0x180050c1d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180050c3f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180050c3f`
- `KERNEL32!AcquireSRWLockShared` at `0x180050b56`
- `KERNEL32!AcquireSRWLockShared` at `0x180050b56`
- `KERNEL32!ReleaseSRWLockShared` at `0x180050b98`
- `KERNEL32!ReleaseSRWLockShared` at `0x180050bad`
- `KERNEL32!ReleaseSRWLockShared` at `0x180050b98`
- `KERNEL32!ReleaseSRWLockShared` at `0x180050bad`

## pseudocode

```c

```
