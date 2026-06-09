# GetMonitorBrightnessCaps(_DISPLAYCONFIG_GET_MONITOR_INTERNAL_INFO *)

- ea: `0x1400a9918`
- end: `0x1400a9be1`
- name: `?GetMonitorBrightnessCaps@@YAXPEAU_DISPLAYCONFIG_GET_MONITOR_INTERNAL_INFO@@@Z`
- size: `713`
- prototype: `void __fastcall(struct _DISPLAYCONFIG_GET_MONITOR_INTERNAL_INFO *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1400eb71c`

## callees

- `0x1400492a4`
- `0x14004a0d0`
- `0x1400a9918`
- `0x1400ab4f0`
- `0x140238240`
- `0x1402382c0`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1400a9a0b`
- `ntoskrnl!KeInitializeEvent` at `0x1400a9a0b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400a9b62`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400a9b62`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400a9a4d`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400a9a4d`
- `ntoskrnl!IofCallDriver` at `0x1400a9a68`
- `ntoskrnl!IofCallDriver` at `0x1400a9a68`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x1400a99d1`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x1400a99d1`
- `ntoskrnl!ObfDereferenceObject` at `0x1400a9998`
- `ntoskrnl!ObfDereferenceObject` at `0x1400a99ad`
- `ntoskrnl!ObfDereferenceObject` at `0x1400a9998`
- `ntoskrnl!ObfDereferenceObject` at `0x1400a99ad`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1400a9955`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1400a9955`

## pseudocode

```c

```
