# SystemThread::MakeMicroSOSThread(void *,__int64,void * * const,Worker * const,SOS_Task * const,int * const,SOS_Scheduler * const,IMemObj *)

- ea: `0x1004357d0`
- end: `0x1004359ac`
- name: `?MakeMicroSOSThread@SystemThread@@SAXPEAX_JQEAPEAXQEAVWorker@@QEAVSOS_Task@@QEAHQEAVSOS_Scheduler@@PEAVIMemObj@@@Z`
- size: `476`
- prototype: `static void(void *, __int64, void **const, struct Worker *const, struct SOS_Task *const, int *const, struct SOS_Scheduler *const, struct IMemObj *)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x100435660`

## callees

- `0x100404bf2`
- `0x100406340`
- `0x100406510`
- `0x1004067b0`
- `0x1004093f0`
- `0x100410810`
- `0x100434d70`
- `0x1004357d0`
- `0x1004359c0`
- `0x1004371b0`
- `0x100475600`
- `0x100475810`
- `0x100475a50`
- `0x100475b60`
- `0x1004795c0`

## import_xrefs

- `KERNEL32!VirtualProtect` at `0x10048f79e`
- `KERNEL32!VirtualProtect` at `0x10048f79e`
- `KERNEL32!QueryPerformanceCounter` at `0x1004358b1`
- `KERNEL32!QueryPerformanceCounter` at `0x10048f609`
- `KERNEL32!QueryPerformanceCounter` at `0x10048f646`
- `KERNEL32!QueryPerformanceCounter` at `0x10048f8bf`
- `KERNEL32!QueryPerformanceCounter` at `0x10048f8fd`
- `KERNEL32!QueryPerformanceCounter` at `0x10048fa8c`
- `KERNEL32!QueryPerformanceCounter` at `0x10048fac9`
- `KERNEL32!QueryPerformanceCounter` at `0x1004358b1`
- `KERNEL32!QueryPerformanceCounter` at `0x10048f609`
- `KERNEL32!QueryPerformanceCounter` at `0x10048f646`
- `KERNEL32!QueryPerformanceCounter` at `0x10048f8bf`
- `KERNEL32!QueryPerformanceCounter` at `0x10048f8fd`
- `KERNEL32!QueryPerformanceCounter` at `0x10048fa8c`
- `KERNEL32!QueryPerformanceCounter` at `0x10048fac9`
- `KERNEL32!CloseHandle` at `0x10048f3ec`
- `KERNEL32!CloseHandle` at `0x10048f3ec`
- `KERNEL32!VirtualFree` at `0x10048f9d6`
- `KERNEL32!VirtualFree` at `0x10048f9d6`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10048f83b`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10048f97d`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10048f83b`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10048f97d`

## pseudocode

```c

```
