# GetMonitorBrightnessCaps(_DISPLAYCONFIG_GET_MONITOR_INTERNAL_INFO *)

- ea: `0x1400c41e8`
- end: `0x1400c44b1`
- name: `?GetMonitorBrightnessCaps@@YAXPEAU_DISPLAYCONFIG_GET_MONITOR_INTERNAL_INFO@@@Z`
- size: `713`
- prototype: `void __fastcall(struct _DISPLAYCONFIG_GET_MONITOR_INTERNAL_INFO *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1400ee09c`

## callees

- `0x140040394`
- `0x1400411c0`
- `0x1400c41e8`
- `0x1400c5dc0`
- `0x140238bf0`
- `0x140238c40`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1400c42db`
- `ntoskrnl!KeInitializeEvent` at `0x1400c42db`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400c4432`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400c4432`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400c431d`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400c431d`
- `ntoskrnl!IofCallDriver` at `0x1400c4338`
- `ntoskrnl!IofCallDriver` at `0x1400c4338`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x1400c42a1`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x1400c42a1`
- `ntoskrnl!ObfDereferenceObject` at `0x1400c4268`
- `ntoskrnl!ObfDereferenceObject` at `0x1400c427d`
- `ntoskrnl!ObfDereferenceObject` at `0x1400c4268`
- `ntoskrnl!ObfDereferenceObject` at `0x1400c427d`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1400c4225`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1400c4225`

## pseudocode

```c

```
