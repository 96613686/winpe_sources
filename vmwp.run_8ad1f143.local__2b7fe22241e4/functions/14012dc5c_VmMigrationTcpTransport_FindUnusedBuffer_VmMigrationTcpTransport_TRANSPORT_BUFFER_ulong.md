# VmMigrationTcpTransport::FindUnusedBuffer(VmMigrationTcpTransport::_TRANSPORT_BUFFER * *,ulong)

- ea: `0x14012dc5c`
- end: `0x14012dd8e`
- name: `?FindUnusedBuffer@VmMigrationTcpTransport@@IEAAJPEAPEAU_TRANSPORT_BUFFER@1@K@Z`
- size: `306`
- prototype: `__int64 __fastcall(VmMigrationTcpTransport *__hidden this, struct VmMigrationTcpTransport::_TRANSPORT_BUFFER **, DWORD dwMilliseconds)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14012d738`
- `0x14012d840`
- `0x1401debf0`

## callees

- `0x14006af58`
- `0x140095d8c`
- `0x14009d7cc`
- `0x14009fa0c`
- `0x14012dc5c`
- `0x140132960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x14012dca8`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x14012dca8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14012dce9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14012dce9`

## string_xrefs

- `0x14012dcd8`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14012dcfd`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14012dd19`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14012dd3e`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`
- `0x14012dd62`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`

## pseudocode

```c

```
