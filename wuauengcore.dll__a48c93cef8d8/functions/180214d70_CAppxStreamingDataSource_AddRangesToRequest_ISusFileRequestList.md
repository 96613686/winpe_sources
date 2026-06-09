# CAppxStreamingDataSource::AddRangesToRequest(ISusFileRequestList *)

- ea: `0x180214d70`
- end: `0x18021520c`
- name: `?AddRangesToRequest@CAppxStreamingDataSource@@MEAAJPEAUISusFileRequestList@@@Z`
- size: `1180`
- prototype: `__int64 __fastcall(CAppxStreamingDataSource *__hidden this, struct ISusFileRequestList *)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, loader_planting, installer_update`

## callees

- `0x180113ae8`
- `0x1801142c4`
- `0x180116648`
- `0x18012b618`
- `0x1801b75f0`
- `0x1801f1c0c`
- `0x180205b90`
- `0x180214d70`
- `0x180215214`
- `0x18021c418`
- `0x18021c4cc`
- `0x18021c654`
- `0x18021ca58`
- `0x18021ce04`
- `0x180222258`
- `0x180238960`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180214e2a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180214f01`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180214fa6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180214e2a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180214f01`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180214fa6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180214f25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18021515d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180214f25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18021515d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180214f4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180214f4c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180214f46`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180214f46`
- `OLEAUT32!__imp_SysFreeString` at `0x18021516f`
- `OLEAUT32!__imp_SysFreeString` at `0x180215179`
- `OLEAUT32!__imp_SysFreeString` at `0x18021516f`
- `OLEAUT32!__imp_SysFreeString` at `0x180215179`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180214df2`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180214df2`

## string_xrefs

- `0x18021512f`: `SaveBlockTableExtension`
- `0x180214e5a`: `Failed to reset pending blocks for update %ws (sandbox dir: %ws) with error %lx; Aborting AddRangesToRequest`
- `0x180214f64`: `DeleteFile(%ws) failed`
- `0x18021519d`: `AddRangesToRequest for update %ws failed, hr=%#08x`

## pseudocode

```c

```
