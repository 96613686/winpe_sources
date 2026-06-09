# RIMConfigureDeviceFeedback

- ea: `0x140200260`
- end: `0x1402006c9`
- name: `RIMConfigureDeviceFeedback`
- size: `1129`
- prototype: `__int64 __fastcall(struct RIMDEV *)`
- caller_count: `4`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1400bdf08`
- `0x1401cf4b4`
- `0x140211660`
- `0x1402116c4`

## callees

- `0x14004a0d0`
- `0x14004d770`
- `0x1400729c8`
- `0x140072a90`
- `0x1400be4ec`
- `0x1400be6e0`
- `0x140153778`
- `0x14015ebd0`
- `0x14018f0cc`
- `0x140200260`
- `0x1402382c0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1402005f2`
- `ntoskrnl!ZwClose` at `0x1402005f2`
- `ntoskrnl!KeInitializeEvent` at `0x140200428`
- `ntoskrnl!KeInitializeEvent` at `0x140200428`
- `ntoskrnl!KeWaitForSingleObject` at `0x14020057f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14020057f`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140200472`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140200472`
- `ntoskrnl!IofCallDriver` at `0x140200554`
- `ntoskrnl!IofCallDriver` at `0x140200554`
- `ntoskrnl!ObfDereferenceObject` at `0x1402005e2`
- `ntoskrnl!ObfDereferenceObject` at `0x1402005e2`
- `WIN32K!W32GetUserSessionState` at `0x1402002d7`
- `WIN32K!W32GetUserSessionState` at `0x1402004cf`
- `WIN32K!W32GetUserSessionState` at `0x140200666`
- `WIN32K!W32GetUserSessionState` at `0x1402002d7`
- `WIN32K!W32GetUserSessionState` at `0x1402004cf`
- `WIN32K!W32GetUserSessionState` at `0x140200666`
- `HIDPARSE!HidP_SetUsageValue` at `0x1402003b6`
- `HIDPARSE!HidP_SetUsageValue` at `0x1402003b6`
- `HAL!KeQueryPerformanceCounter` at `0x140200593`
- `HAL!KeQueryPerformanceCounter` at `0x140200593`

## string_xrefs

- `0x140200539`: `ConfigDeviceFeedback`

## pseudocode

```c

```
