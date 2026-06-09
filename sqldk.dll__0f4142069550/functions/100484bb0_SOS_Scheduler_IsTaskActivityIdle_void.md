# SOS_Scheduler::IsTaskActivityIdle(void)

- ea: `0x100484bb0`
- end: `0x100486346`
- name: `?IsTaskActivityIdle@SOS_Scheduler@@QEAAHXZ`
- size: `6038`
- prototype: `__int64 __fastcall(SOS_Scheduler *__hidden this)`
- caller_count: `3`
- callee_count: `18`
- tags: `service_task`

## callers

- `0x100472f00`
- `0x100473220`
- `0x100551880`

## callees

- `0x100406340`
- `0x100406510`
- `0x1004067b0`
- `0x100410010`
- `0x100410810`
- `0x10041db40`
- `0x1004360f0`
- `0x1004371b0`
- `0x10046baf0`
- `0x10046bd30`
- `0x100475600`
- `0x100475810`
- `0x100475a50`
- `0x100475b60`
- `0x1004795c0`
- `0x100484bb0`
- `0x100487c20`
- `0x1004beee0`

## import_xrefs

- `KERNEL32!VirtualProtect` at `0x10048518a`
- `KERNEL32!VirtualProtect` at `0x10048571d`
- `KERNEL32!VirtualProtect` at `0x100485c3e`
- `KERNEL32!VirtualProtect` at `0x10048616e`
- `KERNEL32!VirtualProtect` at `0x10048518a`
- `KERNEL32!VirtualProtect` at `0x10048571d`
- `KERNEL32!VirtualProtect` at `0x100485c3e`
- `KERNEL32!VirtualProtect` at `0x10048616e`
- `KERNEL32!QueryPerformanceCounter` at `0x100484d16`
- `KERNEL32!QueryPerformanceCounter` at `0x100484d5f`
- `KERNEL32!QueryPerformanceCounter` at `0x100484ee8`
- `KERNEL32!QueryPerformanceCounter` at `0x100484f32`
- `KERNEL32!QueryPerformanceCounter` at `0x1004850b8`
- `KERNEL32!QueryPerformanceCounter` at `0x100485100`
- `KERNEL32!QueryPerformanceCounter` at `0x1004853f1`
- `KERNEL32!QueryPerformanceCounter` at `0x10048543a`
- `KERNEL32!QueryPerformanceCounter` at `0x100485652`
- `KERNEL32!QueryPerformanceCounter` at `0x10048569a`
- `KERNEL32!QueryPerformanceCounter` at `0x100485992`
- `KERNEL32!QueryPerformanceCounter` at `0x1004859d9`
- `KERNEL32!QueryPerformanceCounter` at `0x100485b73`
- `KERNEL32!QueryPerformanceCounter` at `0x100485bbb`
- `KERNEL32!QueryPerformanceCounter` at `0x100485e9a`
- `KERNEL32!QueryPerformanceCounter` at `0x100485ee1`
- `KERNEL32!QueryPerformanceCounter` at `0x10048609c`
- `KERNEL32!QueryPerformanceCounter` at `0x1004860e4`
- `KERNEL32!QueryPerformanceCounter` at `0x100484d16`
- `KERNEL32!QueryPerformanceCounter` at `0x100484d5f`
- `KERNEL32!QueryPerformanceCounter` at `0x100484ee8`
- `KERNEL32!QueryPerformanceCounter` at `0x100484f32`
- `KERNEL32!QueryPerformanceCounter` at `0x1004850b8`
- `KERNEL32!QueryPerformanceCounter` at `0x100485100`
- `KERNEL32!QueryPerformanceCounter` at `0x1004853f1`
- `KERNEL32!QueryPerformanceCounter` at `0x10048543a`
- `KERNEL32!QueryPerformanceCounter` at `0x100485652`
- `KERNEL32!QueryPerformanceCounter` at `0x10048569a`
- `KERNEL32!QueryPerformanceCounter` at `0x100485992`
- `KERNEL32!QueryPerformanceCounter` at `0x1004859d9`
- `KERNEL32!QueryPerformanceCounter` at `0x100485b73`
- `KERNEL32!QueryPerformanceCounter` at `0x100485bbb`
- `KERNEL32!QueryPerformanceCounter` at `0x100485e9a`
- `KERNEL32!QueryPerformanceCounter` at `0x100485ee1`
- `KERNEL32!QueryPerformanceCounter` at `0x10048609c`
- `KERNEL32!QueryPerformanceCounter` at `0x1004860e4`
- `KERNEL32!VirtualFree` at `0x1004852e0`
- `KERNEL32!VirtualFree` at `0x10048588e`
- `KERNEL32!VirtualFree` at `0x100485d7f`
- `KERNEL32!VirtualFree` at `0x1004862ca`
- `KERNEL32!VirtualFree` at `0x1004852e0`
- `KERNEL32!VirtualFree` at `0x10048588e`
- `KERNEL32!VirtualFree` at `0x100485d7f`
- `KERNEL32!VirtualFree` at `0x1004862ca`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100484deb`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100485248`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100485288`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004857d9`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100485816`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100485cfa`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100485d30`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100486226`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10048626b`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100484deb`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100485248`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100485288`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004857d9`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100485816`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100485cfa`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100485d30`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100486226`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10048626b`

## pseudocode

```c

```
