# VmMigrationTcpTransport::FindUnusedBuffer(VmMigrationTcpTransport::_TRANSPORT_BUFFER * *,ulong)

- ea: `0x1400a2634`
- end: `0x1400a2766`
- name: `?FindUnusedBuffer@VmMigrationTcpTransport@@IEAAJPEAPEAU_TRANSPORT_BUFFER@1@K@Z`
- size: `306`
- prototype: `__int64 __fastcall(VmMigrationTcpTransport *__hidden this, struct VmMigrationTcpTransport::_TRANSPORT_BUFFER **, DWORD dwMilliseconds)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400a2c10`
- `0x1400a2f0c`
- `0x1401ce2a0`

## callees

- `0x140064f4c`
- `0x140078628`
- `0x14007f2a0`
- `0x1400a2634`
- `0x1400ba144`
- `0x14011ea40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1400a2680`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1400a2680`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400a26c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400a26c1`

## string_xrefs

- `0x1400a26b0`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x1400a26d5`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x1400a26f1`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x1400a2716`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x1400a273a`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`

## pseudocode

```c

```
