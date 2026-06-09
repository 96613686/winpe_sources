# COSAsyncDownloader::GetOrCreateDownloader(tagDSGlobalUpdateId const &,wchar_t const *,bool,COSDownloader * *)

- ea: `0x180025da0`
- end: `0x180025f8f`
- name: `?GetOrCreateDownloader@COSAsyncDownloader@@AEAAJAEBUtagDSGlobalUpdateId@@PEB_W_NPEAPEAVCOSDownloader@@@Z`
- size: `495`
- prototype: `__int64 __fastcall(COSAsyncDownloader *__hidden this, const struct tagDSGlobalUpdateId *, const wchar_t *, bool, struct COSDownloader **)`
- caller_count: `5`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x1800249d0`
- `0x180024ac0`
- `0x1800250b0`
- `0x180025180`
- `0x180025ce0`

## callees

- `0x180003950`
- `0x180005f64`
- `0x18000b334`
- `0x180018600`
- `0x180025da0`
- `0x180026008`
- `0x1800261c4`
- `0x1800430f8`
- `0x180049260`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025f1a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025f1a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025deb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025deb`

## pseudocode

```c

```
