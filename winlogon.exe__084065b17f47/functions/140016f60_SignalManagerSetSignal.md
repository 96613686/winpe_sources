# SignalManagerSetSignal

- ea: `0x140016f60`
- end: `0x140017238`
- name: `SignalManagerSetSignal`
- size: `728`
- prototype: `__int64 __fastcall(PRTL_CRITICAL_SECTION CriticalSection)`
- caller_count: `23`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140003b60`
- `0x140003ea0`
- `0x140004470`
- `0x140010e90`
- `0x140011490`
- `0x1400129f0`
- `0x1400146a0`
- `0x140015820`
- `0x140015ba0`
- `0x140016b50`
- `0x140016f30`
- `0x140017240`
- `0x140018e10`
- `0x140036810`
- `0x140037a10`
- `0x140039f70`
- `0x14003b254`
- `0x14003cbd0`
- `0x14003e150`
- `0x14003e92c`
- `0x14003f6cc`
- `0x140041190`
- `0x140044c90`

## callees

- `0x1400057f4`
- `0x140016f60`
- `0x14004df08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140016fc9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140016fc9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400171b7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400171b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016fd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140016fd3`
- `ntdll!RtlLeaveCriticalSection` at `0x140017216`
- `ntdll!RtlLeaveCriticalSection` at `0x14009d83d`
- `ntdll!RtlLeaveCriticalSection` at `0x140017216`
- `ntdll!RtlLeaveCriticalSection` at `0x14009d83d`
- `ntdll!RtlEnterCriticalSection` at `0x140016fbf`
- `ntdll!RtlEnterCriticalSection` at `0x140016fbf`

## pseudocode

```c

```
