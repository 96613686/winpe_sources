# SAL2::CSALCache::InternalPendRead(SAL2::CSALCacheMemMgr::SAL_CACHE_PAGEBUF_REF *,SAL2::ISALIoMgr::IoComplete *)

- ea: `0x18009691c`
- end: `0x180096a8e`
- name: `?InternalPendRead@CSALCache@SAL2@@AEAAJPEAUSAL_CACHE_PAGEBUF_REF@CSALCacheMemMgr@2@PEAVIoComplete@ISALIoMgr@2@@Z`
- size: `370`
- prototype: `__int64 __fastcall(SAL2::CSALCache *__hidden this, struct SAL2::CSALCacheMemMgr::SAL_CACHE_PAGEBUF_REF *, struct SAL2::ISALIoMgr::IoComplete *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800979fc`

## callees

- `0x1800627f0`
- `0x180092d8c`
- `0x1800936a8`
- `0x180095ae8`
- `0x18009642c`
- `0x18009691c`
- `0x180097c10`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180096951`
- `KERNEL32!LeaveCriticalSection` at `0x180096951`
- `KERNEL32!EnterCriticalSection` at `0x18009693c`
- `KERNEL32!EnterCriticalSection` at `0x18009693c`

## string_xrefs

- `0x180096a6c`: `multimedia\dshow\filters\sbe\sal\salcache.cpp`

## pseudocode

```c

```
