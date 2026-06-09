# MemoryManager::CreateAperture(void *,unsigned __int64,unsigned __int64,_VID_PPM_ACCESS_INFO *,void * &,void * &,ushort const *)

- ea: `0x140044290`
- end: `0x1400444b1`
- name: `?CreateAperture@MemoryManager@@UEAAJPEAX_K1PEAT_VID_PPM_ACCESS_INFO@@AEAPEAX3PEBG@Z`
- size: `545`
- prototype: `__int64 __fastcall(MemoryManager *__hidden this, void *, unsigned __int64, unsigned __int64, union _VID_PPM_ACCESS_INFO *, void **, void **, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140042260`
- `0x140044290`
- `0x14005497c`
- `0x140078cb8`
- `0x14009fa0c`
- `0x140132960`
- `0x140132d50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400442ef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400442ef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140044395`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140044395`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400443c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400443c2`
- `vid!VidMapMemoryBlockPageRangeEx` at `0x140044332`
- `vid!VidMapMemoryBlockPageRangeEx` at `0x140044332`
- `vid!VidUnmapMemoryBlockPageRange` at `0x14004449b`
- `vid!VidUnmapMemoryBlockPageRange` at `0x14004449b`

## pseudocode

```c

```
