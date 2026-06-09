# VmmsSwitchStatsPanel::NicVRSSCollectData(void)

- ea: `0x1400b5c84`
- end: `0x1400b6855`
- name: `?NicVRSSCollectData@VmmsSwitchStatsPanel@@AEAAXXZ`
- size: `3025`
- prototype: `void __fastcall(VmmsSwitchStatsPanel *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x140639180`

## callees

- `0x140034404`
- `0x14005c630`
- `0x14006f910`
- `0x1400a8824`
- `0x1400b5c84`
- `0x1401843d8`
- `0x1402895a4`
- `0x1404828e0`
- `0x140482b74`
- `0x1404835a0`
- `0x140638f00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400b62ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400b62ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400b5cee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400b5cee`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x1400b5ded`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x1400b5e2f`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x1400b5e76`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x1400b5ec0`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x1400b5ded`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x1400b5e2f`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x1400b5e76`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x1400b5ec0`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x1400b5f0f`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x1400b5f5b`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x1400b5faf`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x1400b5ffb`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x1400b604f`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x1400b609b`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x1400b60ef`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x1400b613b`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x1400b618f`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x1400b61db`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x1400b622f`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x1400b627e`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x1400b5f0f`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x1400b5f5b`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x1400b5faf`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x1400b5ffb`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x1400b604f`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x1400b609b`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x1400b60ef`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x1400b613b`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x1400b618f`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x1400b61db`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x1400b622f`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x1400b627e`

## string_xrefs

- `0x1400b67fe`: `Failed to set the "Send Complete CPU Deviation Total" counter for the %s instance # %d; error status: %d`
- `0x1400b6837`: `Failed to set the "Send Complete CPU Deviation Per Second" counter for the %s instance # %d; error status: %d`
- `0x1400b66a2`: `Failed to set the "Send Completes Per Second" counter for the %s instance # %d; error status: %d`
- `0x1400b66dd`: `Failed to set the "Send Completes Total" counter for the %s instance # %d; error status: %d`

## pseudocode

```c

```
