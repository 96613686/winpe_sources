# _InitializeVolume(UdmCreateDataSessionControls &,CallHistoryDataSession * *)

- ea: `0x1800627bc`
- end: `0x1800629bb`
- name: `?_InitializeVolume@@YAJAEAUUdmCreateDataSessionControls@@PEAPEAVCallHistoryDataSession@@@Z`
- size: `511`
- prototype: `__int64 __fastcall(struct UdmCreateDataSessionControls *, struct CallHistoryDataSession **)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, service_task`

## callers

- `0x180030180`

## callees

- `0x180008380`
- `0x180008f0c`
- `0x18003c364`
- `0x1800627bc`
- `0x1800629c4`
- `0x180062cf4`
- `0x180062d74`
- `0x180072ccc`
- `0x180076664`
- `0x18007be1c`
- `0x1800977c4`
- `0x18012c76a`
- `0x18012c7b0`

## import_xrefs

- `ESENT!JetBeginSessionA` at `0x18006290d`
- `ESENT!JetBeginSessionA` at `0x18006290d`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800628a0`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800628a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180062865`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180062865`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180062838`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180062838`

## string_xrefs

- `0x18006295e`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x180062980`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`

## pseudocode

```c

```
