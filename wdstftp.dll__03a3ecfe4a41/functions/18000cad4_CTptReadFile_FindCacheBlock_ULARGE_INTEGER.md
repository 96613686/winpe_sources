# CTptReadFile::FindCacheBlock(_ULARGE_INTEGER)

- ea: `0x18000cad4`
- end: `0x18000cb61`
- name: `?FindCacheBlock@CTptReadFile@@AEAAPEAUCacheBlock@1@T_ULARGE_INTEGER@@@Z`
- size: `141`
- prototype: `struct CTptReadFile::CacheBlock *__fastcall(LPCRITICAL_SECTION lpCriticalSection, union _ULARGE_INTEGER)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000cdd0`
- `0x18000cf38`

## callees

- `0x18000cad4`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000caeb`
- `KERNEL32!EnterCriticalSection` at `0x18000caeb`
- `KERNEL32!LeaveCriticalSection` at `0x18000cb42`
- `KERNEL32!LeaveCriticalSection` at `0x18000cb42`

## pseudocode

```c

```
