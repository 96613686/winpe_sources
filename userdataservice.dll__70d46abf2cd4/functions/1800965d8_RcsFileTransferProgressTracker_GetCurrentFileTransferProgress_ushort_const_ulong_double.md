# RcsFileTransferProgressTracker::GetCurrentFileTransferProgress(ushort const *,ulong,double *)

- ea: `0x1800965d8`
- end: `0x180096770`
- name: `?GetCurrentFileTransferProgress@RcsFileTransferProgressTracker@@QEAAJPEBGKPEAN@Z`
- size: `408`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, const unsigned __int16 *, unsigned int, double *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800cb6bc`

## callees

- `0x180008f0c`
- `0x18006db44`
- `0x180072ccc`
- `0x180090804`
- `0x180094eb4`
- `0x1800965d8`
- `0x1800a847c`
- `0x1800fbd68`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18009664d`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18009664d`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18009661b`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18009661b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180096671`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180096671`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800966c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009675b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800966c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009675b`

## string_xrefs

- `0x1800966e7`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\rcsfiletransferprogresstracker.cpp`
- `0x18009672d`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\rcsfiletransferprogresstracker.cpp`
- `0x180096742`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\rcsfiletransferprogresstracker.cpp`

## pseudocode

```c

```
