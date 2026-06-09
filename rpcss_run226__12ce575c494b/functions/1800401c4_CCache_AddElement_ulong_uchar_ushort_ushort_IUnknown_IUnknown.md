# CCache::AddElement(ulong,uchar *,ushort,ushort *,IUnknown *,IUnknown * *)

- ea: `0x1800401c4`
- end: `0x18004056c`
- name: `?AddElement@CCache@@QEAAJKPEAEGPEAGPEAUIUnknown@@PEAPEAU2@@Z`
- size: `936`
- prototype: `__int64 __usercall@<rax>(PSRWLOCK SRWLock@<rcx>, unsigned int@<edx>, unsigned __int8 *@<r8>, unsigned __int16@<r9w>, unsigned __int16 *, struct IUnknown *, struct IUnknown **)`
- caller_count: `7`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18003ffd0`
- `0x180041a30`
- `0x18006ce10`
- `0x18007c1e0`
- `0x18007fb08`
- `0x1800c8cf0`
- `0x1800ca424`

## callees

- `0x18000d4c4`
- `0x18000d97c`
- `0x180034540`
- `0x1800401c4`
- `0x180040c44`
- `0x180040e7c`
- `0x18007e3d4`
- `0x18009e4c4`
- `0x1800b3128`
- `0x180100920`
- `0x18010a078`
- `0x18010a084`
- `0x18010b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040496`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040496`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004038d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800404c2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004038d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800404c2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004029d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004029d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800403dd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040425`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800404d8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040541`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800403dd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040425`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800404d8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040541`

## string_xrefs

- `0x18004025b`: `onecore\com\combase\catalog\cache.cxx`
- `0x180040242`: `Failed to initialize cache eviction state: %!HRESULT!`
- `0x180040254`: `CCache::AddElement`

## pseudocode

```c

```
