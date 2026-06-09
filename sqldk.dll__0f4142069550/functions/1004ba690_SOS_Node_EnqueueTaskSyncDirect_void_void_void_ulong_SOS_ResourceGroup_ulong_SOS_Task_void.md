# SOS_Node::EnqueueTaskSyncDirect(void * (*)(void *),void *,ulong,SOS_ResourceGroup *,ulong,SOS_Task * *,void * *)

- ea: `0x1004ba690`
- end: `0x1004bb357`
- name: `?EnqueueTaskSyncDirect@SOS_Node@@QEAA?AW4SOS_RESULT@@P6APEAXPEAX@Z0KPEAVSOS_ResourceGroup@@KPEAPEAVSOS_Task@@PEAPEAX@Z`
- size: `3271`
- prototype: `enum SOS_RESULT __high(void *(__high *)(void *), void *, unsigned int, struct SOS_ResourceGroup *, unsigned int, struct SOS_Task **, void **)`
- caller_count: `1`
- callee_count: `17`
- tags: `service_task`

## callers

- `0x1004b36c0`

## callees

- `0x100403070`
- `0x100403990`
- `0x100406340`
- `0x100406510`
- `0x1004067b0`
- `0x100410810`
- `0x100410c70`
- `0x1004208d0`
- `0x1004360f0`
- `0x1004371b0`
- `0x100475600`
- `0x100475810`
- `0x100475a50`
- `0x100475b60`
- `0x1004795c0`
- `0x10047aa20`
- `0x1004ba690`

## import_xrefs

- `KERNEL32!VirtualProtect` at `0x1004bac50`
- `KERNEL32!VirtualProtect` at `0x1004bb185`
- `KERNEL32!VirtualProtect` at `0x1004bac50`
- `KERNEL32!VirtualProtect` at `0x1004bb185`
- `KERNEL32!QueryPerformanceCounter` at `0x1004ba98a`
- `KERNEL32!QueryPerformanceCounter` at `0x1004ba9d4`
- `KERNEL32!QueryPerformanceCounter` at `0x1004bab80`
- `KERNEL32!QueryPerformanceCounter` at `0x1004babd1`
- `KERNEL32!QueryPerformanceCounter` at `0x1004baecc`
- `KERNEL32!QueryPerformanceCounter` at `0x1004baf15`
- `KERNEL32!QueryPerformanceCounter` at `0x1004bb0b5`
- `KERNEL32!QueryPerformanceCounter` at `0x1004bb106`
- `KERNEL32!QueryPerformanceCounter` at `0x1004ba98a`
- `KERNEL32!QueryPerformanceCounter` at `0x1004ba9d4`
- `KERNEL32!QueryPerformanceCounter` at `0x1004bab80`
- `KERNEL32!QueryPerformanceCounter` at `0x1004babd1`
- `KERNEL32!QueryPerformanceCounter` at `0x1004baecc`
- `KERNEL32!QueryPerformanceCounter` at `0x1004baf15`
- `KERNEL32!QueryPerformanceCounter` at `0x1004bb0b5`
- `KERNEL32!QueryPerformanceCounter` at `0x1004bb106`
- `KERNEL32!VirtualFree` at `0x1004bada7`
- `KERNEL32!VirtualFree` at `0x1004bb2c9`
- `KERNEL32!VirtualFree` at `0x1004bada7`
- `KERNEL32!VirtualFree` at `0x1004bb2c9`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004bad09`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004bad4a`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004bb23e`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004bb277`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004bad09`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004bad4a`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004bb23e`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004bb277`

## pseudocode

```c

```
