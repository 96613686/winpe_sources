# RIMConfigureTouchpadClickForceSensitivity

- ea: `0x1402006d0`
- end: `0x140200b5b`
- name: `RIMConfigureTouchpadClickForceSensitivity`
- size: `1163`
- prototype: `__int64 __fastcall(struct RIMDEV *, int)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x1400bdf08`
- `0x1401cf4b4`

## callees

- `0x14004a0d0`
- `0x14004d770`
- `0x1400729c8`
- `0x140072a90`
- `0x1400be4ec`
- `0x1400be6e0`
- `0x140153778`
- `0x14015ebd0`
- `0x1401b0b00`
- `0x140200184`
- `0x1402006d0`
- `0x1402382c0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140200a84`
- `ntoskrnl!ZwClose` at `0x140200a84`
- `ntoskrnl!KeInitializeEvent` at `0x1402008a1`
- `ntoskrnl!KeInitializeEvent` at `0x1402008a1`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402009fa`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402009fa`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1402008ec`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1402008ec`
- `ntoskrnl!IofCallDriver` at `0x1402009ce`
- `ntoskrnl!IofCallDriver` at `0x1402009ce`
- `ntoskrnl!ObfDereferenceObject` at `0x140200a73`
- `ntoskrnl!ObfDereferenceObject` at `0x140200a73`
- `WIN32K!W32GetUserSessionState` at `0x140200747`
- `WIN32K!W32GetUserSessionState` at `0x140200949`
- `WIN32K!W32GetUserSessionState` at `0x140200af8`
- `WIN32K!W32GetUserSessionState` at `0x140200747`
- `WIN32K!W32GetUserSessionState` at `0x140200949`
- `WIN32K!W32GetUserSessionState` at `0x140200af8`
- `HIDPARSE!HidP_SetUsageValue` at `0x14020082b`
- `HIDPARSE!HidP_SetUsageValue` at `0x14020082b`
- `HAL!KeQueryPerformanceCounter` at `0x140200a24`
- `HAL!KeQueryPerformanceCounter` at `0x140200a24`

## string_xrefs

- `0x1402009b3`: `ConfigClickForceSens`

## pseudocode

```c

```
