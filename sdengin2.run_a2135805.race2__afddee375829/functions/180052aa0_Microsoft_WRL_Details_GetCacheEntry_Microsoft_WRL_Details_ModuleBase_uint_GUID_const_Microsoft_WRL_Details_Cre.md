# Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)

- ea: `0x180052aa0`
- end: `0x180052c56`
- name: `?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z`
- size: `438`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *__hidden this, struct Microsoft::WRL::Details::ModuleBase *, unsigned int *, const struct _GUID *, PSRWLOCK SRWLock, struct IUnknown **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180050004`

## callees

- `0x180052aa0`
- `0x180053454`
- `0x1800d1010`

## import_xrefs

- `KERNEL32!EncodePointer` at `0x180052bc6`
- `KERNEL32!EncodePointer` at `0x180052bc6`
- `KERNEL32!DecodePointer` at `0x180052b0e`
- `KERNEL32!DecodePointer` at `0x180052bdb`
- `KERNEL32!DecodePointer` at `0x180052b0e`
- `KERNEL32!DecodePointer` at `0x180052bdb`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180052c03`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180052c03`
- `KERNEL32!AcquireSRWLockShared` at `0x180052af6`
- `KERNEL32!AcquireSRWLockShared` at `0x180052af6`
- `KERNEL32!ReleaseSRWLockShared` at `0x180052b44`
- `KERNEL32!ReleaseSRWLockShared` at `0x180052b5f`
- `KERNEL32!ReleaseSRWLockShared` at `0x180052b44`
- `KERNEL32!ReleaseSRWLockShared` at `0x180052b5f`

## pseudocode

```c

```
