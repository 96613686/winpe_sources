# SystemThread::UnmakeMicroSOSThread(Worker * const,SOS_Task * const,int)

- ea: `0x100435230`
- end: `0x10043544e`
- name: `?UnmakeMicroSOSThread@SystemThread@@SAXQEAVWorker@@QEAVSOS_Task@@H@Z`
- size: `542`
- prototype: `void __fastcall(struct Worker *const this, struct SOS_Task *const, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x1004354a0`
- `0x1004b8080`

## callees

- `0x100406340`
- `0x100406510`
- `0x1004067b0`
- `0x1004093f0`
- `0x100410810`
- `0x10042a840`
- `0x100434de0`
- `0x100435230`
- `0x100435460`
- `0x1004371b0`
- `0x100475600`
- `0x100475810`
- `0x100475a50`
- `0x100475b60`
- `0x1004795c0`
- `0x1005b1fc0`

## import_xrefs

- `KERNEL32!VirtualProtect` at `0x10048cfe8`
- `KERNEL32!VirtualProtect` at `0x10048cfe8`
- `KERNEL32!QueryPerformanceCounter` at `0x10048cb8c`
- `KERNEL32!QueryPerformanceCounter` at `0x10048cbc9`
- `KERNEL32!QueryPerformanceCounter` at `0x10048cd13`
- `KERNEL32!QueryPerformanceCounter` at `0x10048cd54`
- `KERNEL32!QueryPerformanceCounter` at `0x10048cf1a`
- `KERNEL32!QueryPerformanceCounter` at `0x10048cf60`
- `KERNEL32!QueryPerformanceCounter` at `0x10048cb8c`
- `KERNEL32!QueryPerformanceCounter` at `0x10048cbc9`
- `KERNEL32!QueryPerformanceCounter` at `0x10048cd13`
- `KERNEL32!QueryPerformanceCounter` at `0x10048cd54`
- `KERNEL32!QueryPerformanceCounter` at `0x10048cf1a`
- `KERNEL32!QueryPerformanceCounter` at `0x10048cf60`
- `KERNEL32!CloseHandle` at `0x1004353e7`
- `KERNEL32!CloseHandle` at `0x100435419`
- `KERNEL32!CloseHandle` at `0x1004353e7`
- `KERNEL32!CloseHandle` at `0x100435419`
- `KERNEL32!VirtualFree` at `0x10048d170`
- `KERNEL32!VirtualFree` at `0x10048d170`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10048cc25`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10048cc25`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10048cc31`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10048cc31`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10048d085`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10048d11b`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10048d085`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10048d11b`

## string_xrefs

- `0x10048d1d0`: `!SystemThread::IsSystemThread()`

## pseudocode

```c

```
