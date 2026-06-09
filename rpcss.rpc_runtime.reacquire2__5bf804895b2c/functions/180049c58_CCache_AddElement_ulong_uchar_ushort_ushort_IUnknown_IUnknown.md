# CCache::AddElement(ulong,uchar *,ushort,ushort *,IUnknown *,IUnknown * *)

- ea: `0x180049c58`
- end: `0x18004a031`
- name: `?AddElement@CCache@@QEAAJKPEAEGPEAGPEAUIUnknown@@PEAPEAU2@@Z`
- size: `985`
- prototype: `__int64 __usercall@<rax>(PSRWLOCK SRWLock@<rcx>, unsigned int@<edx>, unsigned __int8 *@<r8>, unsigned __int16@<r9w>, unsigned __int16 *, struct IUnknown *, struct IUnknown **)`
- caller_count: `7`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180049a64`
- `0x18004b69c`
- `0x180071440`
- `0x180080c80`
- `0x1800846b0`
- `0x1800ced50`
- `0x1800d0484`

## callees

- `0x180026998`
- `0x18002750c`
- `0x180034260`
- `0x180049c58`
- `0x18004a750`
- `0x18004a99c`
- `0x18008172c`
- `0x1800a3784`
- `0x1800b8428`
- `0x180109328`
- `0x180112d78`
- `0x180112d84`
- `0x180114010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049f42`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049f42`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049e27`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049f74`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049e27`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049f74`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049d31`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049d31`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049e7d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049ecb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049f90`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049fff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049e7d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049ecb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049f90`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049fff`

## string_xrefs

- `0x180049cef`: `onecore\com\combase\catalog\cache.cxx`
- `0x180049cd6`: `Failed to initialize cache eviction state: %!HRESULT!`
- `0x180049ce8`: `CCache::AddElement`

## pseudocode

```c

```
