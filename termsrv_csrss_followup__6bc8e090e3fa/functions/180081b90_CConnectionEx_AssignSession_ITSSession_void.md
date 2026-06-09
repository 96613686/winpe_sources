# CConnectionEx::AssignSession(ITSSession *,void *)

- ea: `0x180081b90`
- end: `0x180081d49`
- name: `?AssignSession@CConnectionEx@@UEAAJPEAUITSSession@@PEAX@Z`
- size: `441`
- prototype: `__int64 __fastcall(CConnectionEx *__hidden this, struct ITSSession *, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180009940`
- `0x180015310`
- `0x180033f60`
- `0x180081b90`
- `0x180087c00`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180081bd7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180081c8f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180081bd7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180081c8f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180081c1a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180081c33`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180081cb3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180081c1a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180081c33`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180081cb3`

## string_xrefs

- `0x180081cf4`: `this->ptrIWRdsProtocolConnection->NotifySessionId failed: 0x%x in %s`

## pseudocode

```c

```
