# CAppxStreamingDataSource::AddFullFileToRequest(ISusFileRequestList *,bool)

- ea: `0x180214730`
- end: `0x180214d62`
- name: `?AddFullFileToRequest@CAppxStreamingDataSource@@MEAAJPEAUISusFileRequestList@@_N@Z`
- size: `1586`
- prototype: `__int64 __fastcall(CAppxStreamingDataSource *__hidden this, struct ISusFileRequestList *, bool)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, loader_planting, installer_update`

## callees

- `0x180113ae8`
- `0x1801142c4`
- `0x180116648`
- `0x18012b618`
- `0x1801b75f0`
- `0x1801f1c0c`
- `0x180205b90`
- `0x180214730`
- `0x180215214`
- `0x180216ac0`
- `0x18021c418`
- `0x18021c4cc`
- `0x18021c654`
- `0x18021ca58`
- `0x18021ce04`
- `0x180222258`
- `0x180238960`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1802147f1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1802148f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180214af7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1802147f1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1802148f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180214af7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180214914`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180214cbe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180214914`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180214cbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180214940`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180214940`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18021493a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18021493a`
- `OLEAUT32!__imp_SysFreeString` at `0x180214cd1`
- `OLEAUT32!__imp_SysFreeString` at `0x180214cdb`
- `OLEAUT32!__imp_SysFreeString` at `0x180214cd1`
- `OLEAUT32!__imp_SysFreeString` at `0x180214cdb`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1802147b9`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1802147b9`

## string_xrefs

- `0x18021496b`: `%hs DeleteFile(%ws) failed`
- `0x180214a9b`: `SaveBlockTableExtension`
- `0x180214c90`: `SaveBlockTableExtension`
- `0x180214cf5`: `AddFullFileToRequest for update %ws failed`
- `0x180214821`: `Failed to reset pending blocks for update %ws (sandbox dir: %ws) with error %lx; Aborting AddRangesToRequest`

## pseudocode

```c

```
