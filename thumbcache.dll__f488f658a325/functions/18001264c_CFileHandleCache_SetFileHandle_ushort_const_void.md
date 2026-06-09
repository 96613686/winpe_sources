# CFileHandleCache::SetFileHandle(ushort const *,void *)

- ea: `0x18001264c`
- end: `0x18001283e`
- name: `?SetFileHandle@CFileHandleCache@@QEAAJPEBGPEAX@Z`
- size: `498`
- prototype: `int(CFileHandleCache *__hidden this, const unsigned __int16 *, void *)`
- caller_count: `5`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18000e6a0`
- `0x180010e00`
- `0x180010ee8`
- `0x180028518`
- `0x180028c8c`

## callees

- `0x18000b3c0`
- `0x18001264c`
- `0x180012844`
- `0x1800296d0`
- `0x18002a330`
- `0x18002c870`
- `0x180035830`
- `0x1800364ac`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001270b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012816`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001270b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012816`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800126cb`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800126cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800126a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800126a7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012724`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012724`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001267a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001267a`

## pseudocode

```c

```
