# ApertureManager::CreateGpaAperture(unsigned __int64,unsigned __int64,_VID_PPM_ACCESS_INFO *,ushort const *,void * &,void * &)

- ea: `0x1400419ec`
- end: `0x140041b67`
- name: `?CreateGpaAperture@ApertureManager@@QEAAJ_K0PEAT_VID_PPM_ACCESS_INFO@@PEBGAEAPEAX3@Z`
- size: `379`
- prototype: `__int64 __fastcall(ApertureManager *__hidden this, unsigned __int64, unsigned __int64, union _VID_PPM_ACCESS_INFO *, const unsigned __int16 *, void **, void **)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x140020e18`
- `0x1400be090`
- `0x1400cfd20`

## callees

- `0x1400419ec`
- `0x140041b70`
- `0x140041b94`
- `0x14007f388`
- `0x14011ea40`
- `0x14011ee30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140041a7a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140041a7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140041ae8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140041b59`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140041ae8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140041b59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140041a4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140041a4f`
- `vid!VidUnmapGpaPageRange` at `0x140041b2b`
- `vid!VidUnmapGpaPageRange` at `0x140041b2b`
- `vid!VidMapGpaPageRange` at `0x140041a3f`
- `vid!VidMapGpaPageRange` at `0x140041a3f`

## pseudocode

```c

```
