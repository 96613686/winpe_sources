# ApertureManager::CreateGpaAperture(unsigned __int64,unsigned __int64,_VID_PPM_ACCESS_INFO *,ushort const *,void * &,void * &)

- ea: `0x1400440b8`
- end: `0x140044233`
- name: `?CreateGpaAperture@ApertureManager@@QEAAJ_K0PEAT_VID_PPM_ACCESS_INFO@@PEBGAEAPEAX3@Z`
- size: `379`
- prototype: `__int64 __fastcall(ApertureManager *__hidden this, unsigned __int64, unsigned __int64, union _VID_PPM_ACCESS_INFO *, const unsigned __int16 *, void **, void **)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x1400208ac`
- `0x1400c8c00`
- `0x1400dfc70`

## callees

- `0x1400440b8`
- `0x14004423c`
- `0x140044260`
- `0x140132960`
- `0x140132d50`
- `0x14017297c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140044146`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140044146`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400441b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140044225`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400441b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140044225`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004411b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004411b`
- `vid!VidUnmapGpaPageRange` at `0x1400441f7`
- `vid!VidUnmapGpaPageRange` at `0x1400441f7`
- `vid!VidMapGpaPageRange` at `0x14004410b`
- `vid!VidMapGpaPageRange` at `0x14004410b`

## pseudocode

```c

```
