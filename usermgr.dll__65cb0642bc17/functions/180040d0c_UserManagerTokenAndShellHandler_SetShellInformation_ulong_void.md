# UserManagerTokenAndShellHandler::SetShellInformation(ulong,void *)

- ea: `0x180040d0c`
- end: `0x180040f54`
- name: `?SetShellInformation@UserManagerTokenAndShellHandler@@QEAAJKPEAX@Z`
- size: `584`
- prototype: `__int64 __fastcall(UserManagerTokenAndShellHandler *__hidden this, unsigned int, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800468b0`

## callees

- `0x1800347a0`
- `0x180036248`
- `0x18003e290`
- `0x180040d0c`
- `0x180063e64`
- `0x180063fe8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040f0e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040f2d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040f0e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040f2d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180040eb6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180040eb6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180040d54`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180040e75`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180040d54`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180040e75`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180040de6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180040de6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180040dd2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180040dd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040e4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040ec0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040e4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040ec0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180040e0c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180040e15`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180040e0c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180040e15`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180040e44`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180040e44`

## pseudocode

```c

```
