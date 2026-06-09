# GetMonitorBrightnessCaps(_DISPLAYCONFIG_GET_MONITOR_INTERNAL_INFO *)

- ea: `0x1400d3228`
- end: `0x1400d34f1`
- name: `?GetMonitorBrightnessCaps@@YAXPEAU_DISPLAYCONFIG_GET_MONITOR_INTERNAL_INFO@@@Z`
- size: `713`
- prototype: `void __fastcall(struct _DISPLAYCONFIG_GET_MONITOR_INTERNAL_INFO *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1400f08ac`

## callees

- `0x14007ab04`
- `0x14007b930`
- `0x1400d3228`
- `0x1400d4e00`
- `0x1402389c0`
- `0x140238a40`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1400d331b`
- `ntoskrnl!KeInitializeEvent` at `0x1400d331b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400d3472`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400d3472`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400d335d`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400d335d`
- `ntoskrnl!IofCallDriver` at `0x1400d3378`
- `ntoskrnl!IofCallDriver` at `0x1400d3378`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x1400d32e1`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x1400d32e1`
- `ntoskrnl!ObfDereferenceObject` at `0x1400d32a8`
- `ntoskrnl!ObfDereferenceObject` at `0x1400d32bd`
- `ntoskrnl!ObfDereferenceObject` at `0x1400d32a8`
- `ntoskrnl!ObfDereferenceObject` at `0x1400d32bd`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1400d3265`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1400d3265`

## pseudocode

```c

```
