# Channel::RemoveLegacySubscriber(_IELF_HANDLE *)

- ea: `0x18008d5f8`
- end: `0x18008d683`
- name: `?RemoveLegacySubscriber@Channel@@AEAAXPEAU_IELF_HANDLE@@@Z`
- size: `139`
- prototype: `void __fastcall(RTL_SRWLOCK *this, struct _IELF_HANDLE *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18008d590`

## callees

- `0x18001c320`
- `0x18008d5f8`
- `0x18009eac0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008d67c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008d612`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008d612`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008d622`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008d622`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008d667`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008d667`

## pseudocode

```c

```
