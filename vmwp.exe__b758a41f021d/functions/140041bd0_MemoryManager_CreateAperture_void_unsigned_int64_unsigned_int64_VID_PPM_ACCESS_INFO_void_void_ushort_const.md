# MemoryManager::CreateAperture(void *,unsigned __int64,unsigned __int64,_VID_PPM_ACCESS_INFO *,void * &,void * &,ushort const *)

- ea: `0x140041bd0`
- end: `0x140041df1`
- name: `?CreateAperture@MemoryManager@@UEAAJPEAX_K1PEAT_VID_PPM_ACCESS_INFO@@AEAPEAX3PEBG@Z`
- size: `545`
- prototype: `__int64 __fastcall(MemoryManager *__hidden this, void *, unsigned __int64, unsigned __int64, union _VID_PPM_ACCESS_INFO *, void **, void **, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1400364a0`
- `0x140041bd0`
- `0x1400544a8`
- `0x140064f4c`
- `0x14008a328`
- `0x14011ea40`
- `0x14011ee30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140041c2f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140041c2f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140041cd5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140041cd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140041d02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140041d02`
- `vid!VidMapMemoryBlockPageRangeEx` at `0x140041c72`
- `vid!VidMapMemoryBlockPageRangeEx` at `0x140041c72`
- `vid!VidUnmapMemoryBlockPageRange` at `0x140041ddb`
- `vid!VidUnmapMemoryBlockPageRange` at `0x140041ddb`

## pseudocode

```c

```
