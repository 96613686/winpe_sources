# CThumbnailCache::_ExceptionFilter(uint,_EXCEPTION_POINTERS *,CReadersWriterLock *)

- ea: `0x18004300c`
- end: `0x1800430cd`
- name: `?_ExceptionFilter@CThumbnailCache@@AEAAHIPEAU_EXCEPTION_POINTERS@@PEAVCReadersWriterLock@@@Z`
- size: `193`
- prototype: `__int64 __fastcall(CThumbnailCache *__hidden this, unsigned int, struct _EXCEPTION_POINTERS *, struct CReadersWriterLock *)`
- caller_count: `4`
- callee_count: `8`
- tags: ``

## callers

- `0x18001161c`
- `0x180013d80`
- `0x180014e0c`
- `0x18002e588`

## callees

- `0x18000b9b0`
- `0x1800152b0`
- `0x180020094`
- `0x180035830`
- `0x1800409f8`
- `0x1800417ec`
- `0x180041b68`
- `0x18004300c`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18004306d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180043082`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18004306d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180043082`

## string_xrefs

- `0x180043066`: `*** thumbcache: Reader lock is still held, releasing before resetting cache.\n`
- `0x18004307b`: `*** thumbcache: Exception caught. Resetting all cache files.\n`

## pseudocode

```c

```
