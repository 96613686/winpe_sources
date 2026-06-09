# VmMigrationConnection::FindUnusedDescriptor(VmMigrationConnection::_MESSAGE_BUFFER * *,ulong,int)

- ea: `0x14009fef0`
- end: `0x1400a00b4`
- name: `?FindUnusedDescriptor@VmMigrationConnection@@IEAAJPEAPEAU_MESSAGE_BUFFER@1@KH@Z`
- size: `452`
- prototype: `int(VmMigrationConnection *__hidden this, struct VmMigrationConnection::_MESSAGE_BUFFER **, unsigned int, int)`
- caller_count: `5`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14009f504`
- `0x14009f860`
- `0x1400a039c`
- `0x1400a1bd8`
- `0x1400a2770`

## callees

- `0x1400364a0`
- `0x1400544a8`
- `0x140078628`
- `0x14009fef0`
- `0x1400ba144`
- `0x14011ea40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x14009ff3e`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x14009ff3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14009ff83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14009ff83`

## string_xrefs

- `0x14009ff72`: `onecore\vm\common\migration\vmmigrationconnection.cpp`
- `0x14009ff97`: `onecore\vm\common\migration\vmmigrationconnection.cpp`
- `0x14009ffb3`: `onecore\vm\common\migration\vmmigrationconnection.cpp`
- `0x14009ffcf`: `onecore\vm\common\migration\vmmigrationconnection.cpp`
- `0x1400a0077`: `onecore\vm\common\migration\vmmigrationconnection.cpp`

## pseudocode

```c

```
