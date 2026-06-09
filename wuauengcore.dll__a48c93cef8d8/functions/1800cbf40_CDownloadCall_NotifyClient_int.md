# CDownloadCall::NotifyClient(int *)

- ea: `0x1800cbf40`
- end: `0x1800cc729`
- name: `?NotifyClient@CDownloadCall@@UEAAJPEAH@Z`
- size: `2025`
- prototype: `__int64 __fastcall(CDownloadCall *__hidden this, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x1800cbf40`
- `0x1800cedcc`
- `0x180113ae8`
- `0x18011a14c`
- `0x18012b618`
- `0x180240cc0`
- `0x180240d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cbf9e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cc031`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cc37b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cc641`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cbf9e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cc031`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cc37b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800cc641`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cbfc4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cc180`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cc402`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cc6c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cbfc4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cc180`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cc402`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800cc6c2`

## string_xrefs

- `0x1800cc212`: `Calling DownloadCallback per-update: call %ws; idx %lu; upd: (%I64u/%I64u); call: (%I64u/%I64u)`
- `0x1800cc1a3`: `Resetting per-update download sizes for download call %ws since one of the updates has unknown download size.`
- `0x1800cc3c3`: `Resetting per-call download sizes for download call %ws since one of the updates has unknown download size.`

## pseudocode

```c

```
