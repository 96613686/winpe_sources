# VmMigrationTcpTransport::FlushPendingReceives(ulong)

- ea: `0x140097c24`
- end: `0x140097d90`
- name: `?FlushPendingReceives@VmMigrationTcpTransport@@IEAAJK@Z`
- size: `364`
- prototype: `__int64 __fastcall(VmMigrationTcpTransport *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400976a0`
- `0x1401df540`

## callees

- `0x14004bbec`
- `0x140097c24`
- `0x14009d7cc`
- `0x1400d84a8`
- `0x140132960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140097ce2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140097ce2`
- `WS2_32!WSAGetOverlappedResult` at `0x140097cd2`
- `WS2_32!WSAGetOverlappedResult` at `0x140097cd2`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x140097d00`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x140097d00`

## string_xrefs

- `0x140097d45`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`

## pseudocode

```c

```
