# CSCMProfileCache::GetOrLoadProfile(void *,_GUID *,ushort * *)

- ea: `0x1800861e8`
- end: `0x1800864d3`
- name: `?GetOrLoadProfile@CSCMProfileCache@@QEAAJPEAXPEAU_GUID@@PEAPEAG@Z`
- size: `747`
- prototype: `int(CSCMProfileCache *__hidden this, void *, struct _GUID *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004c4b0`

## callees

- `0x180034260`
- `0x1800710a4`
- `0x18008172c`
- `0x180084150`
- `0x180085cf4`
- `0x1800861e8`
- `0x1800871cc`
- `0x1800b7ac0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008629a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008633b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008629a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008633b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180086496`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180086496`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800863f9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800863f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008646a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008646a`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18008628a`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18008628a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180086396`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180086396`
- `SspiCli!GetUserNameExW` at `0x180086324`
- `SspiCli!GetUserNameExW` at `0x180086324`

## string_xrefs

- `0x1800862fa`: `onecore\com\combase\rpcss\olescm\profiles.cxx`
- `0x180086386`: `onecore\com\combase\rpcss\olescm\profiles.cxx`
- `0x1800862eb`: `CSCMProfileCache::GetOrLoadProfile`
- `0x18008637a`: `CSCMProfileCache::GetOrLoadProfile`

## pseudocode

```c

```
