# RIMConfigureTouchpadClickForceSensitivity

- ea: `0x140200ef0`
- end: `0x14020137b`
- name: `RIMConfigureTouchpadClickForceSensitivity`
- size: `1163`
- prototype: `__int64 __fastcall(struct RIMDEV *, int)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x1400d7618`
- `0x1401cfa14`

## callees

- `0x1400411c0`
- `0x1400449b0`
- `0x140071828`
- `0x1400718f0`
- `0x1400d7bfc`
- `0x1400d7df0`
- `0x140152e08`
- `0x14015e1e0`
- `0x1401b1060`
- `0x1402009a4`
- `0x140200ef0`
- `0x140238c40`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1402012a4`
- `ntoskrnl!ZwClose` at `0x1402012a4`
- `ntoskrnl!KeInitializeEvent` at `0x1402010c1`
- `ntoskrnl!KeInitializeEvent` at `0x1402010c1`
- `ntoskrnl!KeWaitForSingleObject` at `0x14020121a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14020121a`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14020110c`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14020110c`
- `ntoskrnl!IofCallDriver` at `0x1402011ee`
- `ntoskrnl!IofCallDriver` at `0x1402011ee`
- `ntoskrnl!ObfDereferenceObject` at `0x140201293`
- `ntoskrnl!ObfDereferenceObject` at `0x140201293`
- `WIN32K!W32GetUserSessionState` at `0x140200f67`
- `WIN32K!W32GetUserSessionState` at `0x140201169`
- `WIN32K!W32GetUserSessionState` at `0x140201318`
- `WIN32K!W32GetUserSessionState` at `0x140200f67`
- `WIN32K!W32GetUserSessionState` at `0x140201169`
- `WIN32K!W32GetUserSessionState` at `0x140201318`
- `HIDPARSE!HidP_SetUsageValue` at `0x14020104b`
- `HIDPARSE!HidP_SetUsageValue` at `0x14020104b`
- `HAL!KeQueryPerformanceCounter` at `0x140201244`
- `HAL!KeQueryPerformanceCounter` at `0x140201244`

## string_xrefs

- `0x1402011d3`: `ConfigClickForceSens`

## pseudocode

```c

```
