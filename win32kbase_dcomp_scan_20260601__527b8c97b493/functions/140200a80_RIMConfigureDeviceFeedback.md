# RIMConfigureDeviceFeedback

- ea: `0x140200a80`
- end: `0x140200ee9`
- name: `RIMConfigureDeviceFeedback`
- size: `1129`
- prototype: `__int64 __fastcall(struct RIMDEV *)`
- caller_count: `4`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1400d7618`
- `0x1401cfa14`
- `0x140211e80`
- `0x140211ee4`

## callees

- `0x1400411c0`
- `0x1400449b0`
- `0x140071828`
- `0x1400718f0`
- `0x1400d7bfc`
- `0x1400d7df0`
- `0x140152e08`
- `0x14015e1e0`
- `0x14018ef4c`
- `0x140200a80`
- `0x140238c40`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140200e12`
- `ntoskrnl!ZwClose` at `0x140200e12`
- `ntoskrnl!KeInitializeEvent` at `0x140200c48`
- `ntoskrnl!KeInitializeEvent` at `0x140200c48`
- `ntoskrnl!KeWaitForSingleObject` at `0x140200d9f`
- `ntoskrnl!KeWaitForSingleObject` at `0x140200d9f`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140200c92`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140200c92`
- `ntoskrnl!IofCallDriver` at `0x140200d74`
- `ntoskrnl!IofCallDriver` at `0x140200d74`
- `ntoskrnl!ObfDereferenceObject` at `0x140200e02`
- `ntoskrnl!ObfDereferenceObject` at `0x140200e02`
- `WIN32K!W32GetUserSessionState` at `0x140200af7`
- `WIN32K!W32GetUserSessionState` at `0x140200cef`
- `WIN32K!W32GetUserSessionState` at `0x140200e86`
- `WIN32K!W32GetUserSessionState` at `0x140200af7`
- `WIN32K!W32GetUserSessionState` at `0x140200cef`
- `WIN32K!W32GetUserSessionState` at `0x140200e86`
- `HIDPARSE!HidP_SetUsageValue` at `0x140200bd6`
- `HIDPARSE!HidP_SetUsageValue` at `0x140200bd6`
- `HAL!KeQueryPerformanceCounter` at `0x140200db3`
- `HAL!KeQueryPerformanceCounter` at `0x140200db3`

## string_xrefs

- `0x140200d59`: `ConfigDeviceFeedback`

## pseudocode

```c

```
