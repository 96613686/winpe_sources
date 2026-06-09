# CStorageThumbnailCache::GetThumbnailCache(_GUID const &,void * *)

- ea: `0x18001a000`
- end: `0x18001a0df`
- name: `?GetThumbnailCache@CStorageThumbnailCache@@AEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `223`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180019980`
- `0x18002ff10`

## callees

- `0x180003624`
- `0x18000bfd8`
- `0x18001809c`
- `0x18001a000`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a09e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a0d4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a09e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001a0d4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a04f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001a04f`

## string_xrefs

- `0x18001a085`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`
- `0x18001a0b0`: `onecoreuap\shell\ext\thumbnailcache\lib\thumbcacheapi.cpp`

## pseudocode

```c

```
