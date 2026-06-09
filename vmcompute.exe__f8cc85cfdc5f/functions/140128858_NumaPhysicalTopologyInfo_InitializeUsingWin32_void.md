# NumaPhysicalTopologyInfo::InitializeUsingWin32(void)

- ea: `0x140128858`
- end: `0x140128c13`
- name: `?InitializeUsingWin32@NumaPhysicalTopologyInfo@@AEAAXXZ`
- size: `955`
- prototype: `void __fastcall(NumaPhysicalTopologyInfo *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14023f264`

## callees

- `0x1400451a0`
- `0x140080180`
- `0x1400a1dcc`
- `0x140128858`
- `0x140128c1c`
- `0x1401332f0`
- `0x140134048`
- `0x140142dac`
- `0x140221738`
- `0x14023f154`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x140128907`
- `ntdll!NtQuerySystemInformation` at `0x140128966`
- `ntdll!NtQuerySystemInformation` at `0x140128907`
- `ntdll!NtQuerySystemInformation` at `0x140128966`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1401289d2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1401289d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140128bdb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140128bdb`
- `api-ms-win-core-systemtopology-l1-1-0!GetNumaHighestNodeNumber` at `0x1401288bb`
- `api-ms-win-core-systemtopology-l1-1-0!GetNumaHighestNodeNumber` at `0x1401288bb`
- `api-ms-win-core-kernel32-legacy-l1-1-1!GetNumaProcessorNodeEx` at `0x140128a63`
- `api-ms-win-core-kernel32-legacy-l1-1-1!GetNumaProcessorNodeEx` at `0x140128a63`

## string_xrefs

- `0x1401288d2`: `onecore\vm\common\numa\numaphysicaltopologyinfo.cpp`
- `0x140128924`: `onecore\vm\common\numa\numaphysicaltopologyinfo.cpp`
- `0x140128980`: `onecore\vm\common\numa\numaphysicaltopologyinfo.cpp`
- `0x140128b0d`: `onecore\vm\common\numa\numaphysicaltopologyinfo.cpp`
- `0x1401289ea`: `onecore\vm\common\vml\VmMemory.h`

## pseudocode

```c

```
