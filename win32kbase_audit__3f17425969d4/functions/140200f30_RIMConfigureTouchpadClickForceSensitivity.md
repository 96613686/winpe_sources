# RIMConfigureTouchpadClickForceSensitivity

- ea: `0x140200f30`
- end: `0x1402013bb`
- name: `RIMConfigureTouchpadClickForceSensitivity`
- size: `1163`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, __int64)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x1400b1d68`
- `0x1401d0234`

## callees

- `0x140049df8`
- `0x140049ec0`
- `0x14007b930`
- `0x14007efd0`
- `0x1400b234c`
- `0x1400b2540`
- `0x140156b2c`
- `0x1401610f8`
- `0x1401b1d10`
- `0x1402009e4`
- `0x140200f30`
- `0x140238a40`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1402012e4`
- `ntoskrnl!ZwClose` at `0x1402012e4`
- `ntoskrnl!KeInitializeEvent` at `0x140201101`
- `ntoskrnl!KeInitializeEvent` at `0x140201101`
- `ntoskrnl!KeWaitForSingleObject` at `0x14020125a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14020125a`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14020114c`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14020114c`
- `ntoskrnl!IofCallDriver` at `0x14020122e`
- `ntoskrnl!IofCallDriver` at `0x14020122e`
- `ntoskrnl!ObfDereferenceObject` at `0x1402012d3`
- `ntoskrnl!ObfDereferenceObject` at `0x1402012d3`
- `WIN32K!W32GetUserSessionState` at `0x140200fa7`
- `WIN32K!W32GetUserSessionState` at `0x1402011a9`
- `WIN32K!W32GetUserSessionState` at `0x140201358`
- `WIN32K!W32GetUserSessionState` at `0x140200fa7`
- `WIN32K!W32GetUserSessionState` at `0x1402011a9`
- `WIN32K!W32GetUserSessionState` at `0x140201358`
- `HIDPARSE!HidP_SetUsageValue` at `0x14020108b`
- `HIDPARSE!HidP_SetUsageValue` at `0x14020108b`
- `HAL!KeQueryPerformanceCounter` at `0x140201284`
- `HAL!KeQueryPerformanceCounter` at `0x140201284`

## string_xrefs

- `0x140201213`: `ConfigClickForceSens`

## pseudocode

```c

```
