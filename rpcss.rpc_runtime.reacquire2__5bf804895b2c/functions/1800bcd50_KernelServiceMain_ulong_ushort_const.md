# KernelServiceMain(ulong,ushort * * const)

- ea: `0x1800bcd50`
- end: `0x1800bcf19`
- name: `?KernelServiceMain@@YAXKQEAPEAG@Z`
- size: `457`
- prototype: `void __fastcall(unsigned int, unsigned __int16 **const)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180034260`
- `0x180081818`
- `0x1800a7388`
- `0x1800b8aec`
- `0x1800bcd50`
- `0x1800bd71c`
- `0x1800bd8ec`
- `0x1800be0a4`
- `0x1800f7900`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800bcdb6`
- `ntdll!RtlNtStatusToDosError` at `0x1800bcdb6`
- `RPCRT4!RpcMgmtIsServerListening` at `0x1800bcec2`
- `RPCRT4!RpcMgmtIsServerListening` at `0x1800bcee8`
- `RPCRT4!RpcMgmtIsServerListening` at `0x1800bcec2`
- `RPCRT4!RpcMgmtIsServerListening` at `0x1800bcee8`
- `RPCRT4!RpcServerListen` at `0x1800bce4b`
- `RPCRT4!RpcServerListen` at `0x1800bce4b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bcd7b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bcd7b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800bceda`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800bceda`

## string_xrefs

- `0x1800bcdff`: `onecore\com\combase\rpcss\wrapper\start.cxx`
- `0x1800bceb2`: `onecore\com\combase\rpcss\wrapper\start.cxx`
- `0x1800bcdf8`: `KernelServiceMain`
- `0x1800bceab`: `KernelServiceMain`

## pseudocode

```c

```
