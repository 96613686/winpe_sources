# CSafeSaveHandleManager::_EnsureTempHandle(void)

- ea: `0x180030478`
- end: `0x18003057e`
- name: `?_EnsureTempHandle@CSafeSaveHandleManager@@AEAAJXZ`
- size: `262`
- prototype: `__int64 __fastcall(CSafeSaveHandleManager *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001b070`

## callees

- `0x18000ddd4`
- `0x180012eb4`
- `0x18001b7dc`
- `0x18001c3b0`
- `0x180030478`
- `0x180030584`
- `0x18006bc34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003054c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003054c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800304a9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800304a9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800304a0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800304a0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180030543`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180030543`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003055f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003055f`

## string_xrefs

- `0x18003056e`: `onecore\internal\shell\inc\impersonationutil.h`

## pseudocode

```c

```
