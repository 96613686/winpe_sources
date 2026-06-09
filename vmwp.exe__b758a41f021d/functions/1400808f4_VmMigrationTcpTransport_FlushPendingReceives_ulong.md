# VmMigrationTcpTransport::FlushPendingReceives(ulong)

- ea: `0x1400808f4`
- end: `0x140080a60`
- name: `?FlushPendingReceives@VmMigrationTcpTransport@@IEAAJK@Z`
- size: `364`
- prototype: `__int64 __fastcall(VmMigrationTcpTransport *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140080360`
- `0x1401cebf0`

## callees

- `0x14004a7cc`
- `0x1400808f4`
- `0x1400ba144`
- `0x1400c7608`
- `0x14011ea40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400809b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400809b2`
- `WS2_32!WSAGetOverlappedResult` at `0x1400809a2`
- `WS2_32!WSAGetOverlappedResult` at `0x1400809a2`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x1400809d0`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x1400809d0`

## string_xrefs

- `0x140080a15`: `onecore\vm\common\migration\vmmigrationtcptransport.cpp`

## pseudocode

```c

```
