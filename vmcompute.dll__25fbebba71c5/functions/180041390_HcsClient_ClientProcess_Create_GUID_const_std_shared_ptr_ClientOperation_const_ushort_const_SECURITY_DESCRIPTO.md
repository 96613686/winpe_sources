# HcsClient::ClientProcess::Create(_GUID const &,std::shared_ptr<ClientOperation> const &,ushort const *,_SECURITY_DESCRIPTOR const *)

- ea: `0x180041390`
- end: `0x180041785`
- name: `?Create@ClientProcess@HcsClient@@QEAAXAEBU_GUID@@AEBV?$shared_ptr@VClientOperation@@@std@@PEBGPEBU_SECURITY_DESCRIPTOR@@@Z`
- size: `1013`
- prototype: `__int64 __fastcall(HcsClient::ClientProcess *this, int)`
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180025950`

## callees

- `0x180001700`
- `0x180002f50`
- `0x180003440`
- `0x180003534`
- `0x18000d108`
- `0x18001ed48`
- `0x1800248bc`
- `0x180038d44`
- `0x180039150`
- `0x18003cf54`
- `0x18003d4cc`
- `0x18003e9a0`
- `0x180040d24`
- `0x180040fa0`
- `0x180041054`
- `0x180041390`
- `0x180041b24`
- `0x180042030`
- `0x180086010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004151a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004151a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041539`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041539`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004152b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041719`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004152b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041719`

## string_xrefs

- `0x180041628`: `onecore\vm\compute\dll\lib\core\clientprocess.cpp`
- `0x18004176d`: `onecore\vm\compute\dll\lib\core\clientprocess.cpp`

## pseudocode

```c

```
