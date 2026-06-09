# WorkDispatcher::CreateAndEnqueueTask(SOS_Scheduler *,void *,SOSHost *,SOS_Task * *)

- ea: `0x100410ae0`
- end: `0x100410c5b`
- name: `?CreateAndEnqueueTask@WorkDispatcher@@QEAA?AW4SOS_RESULT@@PEAVSOS_Scheduler@@PEAXPEAVSOSHost@@PEAPEAVSOS_Task@@@Z`
- size: `379`
- prototype: `enum SOS_RESULT __high(struct SOS_Scheduler *, void *, struct SOSHost *, struct SOS_Task **)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update`

## callers

- `0x100410c70`

## callees

- `0x1004097f0`
- `0x1004098e0`
- `0x10040a8f0`
- `0x1004104a0`
- `0x1004106b0`
- `0x100410ae0`
- `0x100475600`
- `0x100475810`
- `0x100475b60`
- `0x100479d50`

## import_xrefs

- `KERNEL32!VirtualProtect` at `0x10047ba21`
- `KERNEL32!VirtualProtect` at `0x10047ba21`
- `KERNEL32!QueryPerformanceCounter` at `0x10047b976`
- `KERNEL32!QueryPerformanceCounter` at `0x10047b9b1`
- `KERNEL32!QueryPerformanceCounter` at `0x10047b976`
- `KERNEL32!QueryPerformanceCounter` at `0x10047b9b1`
- `KERNEL32!VirtualAlloc` at `0x10047ba91`
- `KERNEL32!VirtualAlloc` at `0x10047ba91`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10047ba4e`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10047ba4e`

## string_xrefs

- `0x1004223e6`: `Sql\DkTemp\sos\include\sos.inl`

## pseudocode

```c

```
