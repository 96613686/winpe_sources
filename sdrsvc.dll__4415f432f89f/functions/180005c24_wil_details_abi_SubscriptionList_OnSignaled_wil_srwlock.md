# wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)

- ea: `0x180005c24`
- end: `0x180005ce1`
- name: `?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z`
- size: `189`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002700`
- `0x180002730`
- `0x1800027e0`
- `0x180007eb0`

## callees

- `0x180005c24`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005cc9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005cc9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005c6a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005c6a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005c54`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180005c54`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005c73`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005c73`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180005c3a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180005c3a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005cab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005cab`

## pseudocode

```c

```
