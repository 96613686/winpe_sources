# CSCMProfileCache::GetOrLoadProfile(void *,_GUID *,ushort * *)

- ea: `0x180081d3c`
- end: `0x180081ff2`
- name: `?GetOrLoadProfile@CSCMProfileCache@@QEAAJPEAXPEAU_GUID@@PEAPEAG@Z`
- size: `694`
- prototype: `int(CSCMProfileCache *__hidden this, void *, struct _GUID *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800507c0`

## callees

- `0x180034540`
- `0x18006cb10`
- `0x18007e3d4`
- `0x18007f780`
- `0x1800818cc`
- `0x180081d3c`
- `0x180082d68`
- `0x1800b27e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081de8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081e7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081de8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081e7d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180081fbc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180081fbc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180081f2b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180081f2b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180081f96`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180081f96`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180081dde`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180081dde`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180081ed2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180081ed2`
- `SspiCli!GetUserNameExW` at `0x180081e6c`
- `SspiCli!GetUserNameExW` at `0x180081e6c`

## string_xrefs

- `0x180081e33`: `CSCMProfileCache::GetOrLoadProfile`
- `0x180081eb6`: `CSCMProfileCache::GetOrLoadProfile`
- `0x180081e42`: `onecore\com\combase\rpcss\olescm\profiles.cxx`
- `0x180081ec2`: `onecore\com\combase\rpcss\olescm\profiles.cxx`

## pseudocode

```c

```
