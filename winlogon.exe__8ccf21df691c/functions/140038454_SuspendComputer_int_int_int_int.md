# SuspendComputer(int,int,int,int)

- ea: `0x140038454`
- end: `0x140038552`
- name: `?SuspendComputer@@YAKHHHH@Z`
- size: `254`
- prototype: `unsigned int __fastcall(int, int, int, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400106bc`
- `0x1400858e0`

## callees

- `0x1400057f4`
- `0x14001a200`
- `0x140038454`
- `0x140038560`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140038481`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140038481`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140038470`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140038470`
- `ntdll!TpSimpleTryPost` at `0x1400384de`
- `ntdll!TpSimpleTryPost` at `0x1400384de`
- `ntdll!RtlNtStatusToDosError` at `0x1400384ec`
- `ntdll!RtlNtStatusToDosError` at `0x1400384ec`
- `ext-ms-win-ntuser-keyboard-l1-1-0!GetKeyState` at `0x1400384b3`
- `ext-ms-win-ntuser-keyboard-l1-1-0!GetKeyState` at `0x1400384b3`

## pseudocode

```c

```
