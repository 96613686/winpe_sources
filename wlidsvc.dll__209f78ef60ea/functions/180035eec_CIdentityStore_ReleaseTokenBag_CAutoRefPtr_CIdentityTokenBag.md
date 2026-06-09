# CIdentityStore::ReleaseTokenBag(CAutoRefPtr<CIdentityTokenBag> &)

- ea: `0x180035eec`
- end: `0x18003612d`
- name: `?ReleaseTokenBag@CIdentityStore@@QEAAJAEAV?$CAutoRefPtr@VCIdentityTokenBag@@@@@Z`
- size: `577`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003283c`

## callees

- `0x1800124c4`
- `0x180019690`
- `0x180019780`
- `0x18001a9c0`
- `0x18001ad00`
- `0x180021b28`
- `0x180021bbc`
- `0x180035eec`
- `0x180036134`
- `0x180036160`
- `0x1800361cc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800360db`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800360db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035fdd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036101`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035fdd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036101`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035f53`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035f53`

## string_xrefs

- `0x180035f36`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\identitystore.cpp`
- `0x1800360b2`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\identitystore.cpp`
- `0x180035f12`: `CIdentityStore::ReleaseTokenBag`
- `0x1800360a5`: `Removing token bag for user '%ls' 0x%p - no longer in use.`

## pseudocode

```c

```
