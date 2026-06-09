# VmMigrationConnection::FindUnusedDescriptor(VmMigrationConnection::_MESSAGE_BUFFER * *,ulong,int)

- ea: `0x14008c1c0`
- end: `0x14008c384`
- name: `?FindUnusedDescriptor@VmMigrationConnection@@IEAAJPEAPEAU_MESSAGE_BUFFER@1@KH@Z`
- size: `452`
- prototype: `int(VmMigrationConnection *__hidden this, struct VmMigrationConnection::_MESSAGE_BUFFER **, unsigned int, int)`
- caller_count: `5`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140088f58`
- `0x14008b7d0`
- `0x14008bb30`
- `0x14008c650`
- `0x1400fd500`

## callees

- `0x140042260`
- `0x14005497c`
- `0x14006af58`
- `0x14008c1c0`
- `0x14009d7cc`
- `0x140132960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x14008c20e`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x14008c20e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008c253`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008c253`

## string_xrefs

- `0x14008c242`: `onecore\vm\common\migration\vmmigrationconnection.cpp`
- `0x14008c267`: `onecore\vm\common\migration\vmmigrationconnection.cpp`
- `0x14008c283`: `onecore\vm\common\migration\vmmigrationconnection.cpp`
- `0x14008c29f`: `onecore\vm\common\migration\vmmigrationconnection.cpp`
- `0x14008c347`: `onecore\vm\common\migration\vmmigrationconnection.cpp`

## pseudocode

```c

```
