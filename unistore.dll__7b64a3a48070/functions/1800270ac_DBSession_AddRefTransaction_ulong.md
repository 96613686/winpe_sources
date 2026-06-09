# DBSession::_AddRefTransaction(ulong)

- ea: `0x1800270ac`
- end: `0x18002739d`
- name: `?_AddRefTransaction@DBSession@@AEAAJK@Z`
- size: `753`
- prototype: `__int64 __fastcall(DBSession *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task`

## callers

- `0x180026f40`

## callees

- `0x1800068f0`
- `0x18000f530`
- `0x180011ed0`
- `0x180013c94`
- `0x1800270ac`
- `0x1800273a4`
- `0x180027db0`
- `0x180028258`
- `0x180028778`
- `0x1800396c8`
- `0x180039898`
- `0x180055328`
- `0x1800737b4`
- `0x18007d9c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800270cd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800270cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027196`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027196`
- `ESENT!JetBeginTransaction` at `0x180027228`
- `ESENT!JetBeginTransaction` at `0x180027228`
- `ESENT!JetGetSessionParameter` at `0x180027130`
- `ESENT!JetGetSessionParameter` at `0x180027204`
- `ESENT!JetGetSessionParameter` at `0x180027130`
- `ESENT!JetGetSessionParameter` at `0x180027204`

## string_xrefs

- `0x1800272b0`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbsession.cpp`
- `0x180027353`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbsession.cpp`

## pseudocode

```c

```
