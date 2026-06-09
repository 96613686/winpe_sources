# DBSession::GetTransactionSink(ulong,_GUID const &,IUnknown * *)

- ea: `0x180059bf0`
- end: `0x180059e32`
- name: `?GetTransactionSink@DBSession@@UEAAJKAEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `578`
- prototype: `__int64 __fastcall(DBSession *__hidden this, unsigned int, const struct _GUID *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task`

## callees

- `0x180004220`
- `0x180004440`
- `0x1800068f0`
- `0x180059bf0`
- `0x180059e38`
- `0x18006b264`
- `0x18006c1ac`
- `0x18006fb5c`
- `0x180079030`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180059c17`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180059c17`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180059c53`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180059c53`

## string_xrefs

- `0x180059c79`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbsession.cpp`
- `0x180059d38`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbsession.cpp`
- `0x180059ddd`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbsession.cpp`

## pseudocode

```c

```
