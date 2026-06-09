# CSafeSaveHandleManager::_EnsureMainHandle(void)

- ea: `0x18001b1dc`
- end: `0x18001b4ad`
- name: `?_EnsureMainHandle@CSafeSaveHandleManager@@AEAAJXZ`
- size: `721`
- prototype: `__int64 __fastcall(CSafeSaveHandleManager *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001b070`
- `0x18001b150`

## callees

- `0x18000ddd4`
- `0x18001b1dc`
- `0x18001b7dc`
- `0x18001c3b0`
- `0x1800660e0`
- `0x18006bc34`
- `0x18008c2ec`
- `0x18008c3d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001b324`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001b324`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b217`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b217`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001b20e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001b20e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b31b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b31b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001b391`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001b391`

## string_xrefs

- `0x18001b3a7`: `onecore\internal\shell\inc\impersonationutil.h`

## pseudocode

```c

```
