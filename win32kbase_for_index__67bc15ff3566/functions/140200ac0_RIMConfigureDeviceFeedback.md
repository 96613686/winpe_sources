# RIMConfigureDeviceFeedback

- ea: `0x140200ac0`
- end: `0x140200f29`
- name: `RIMConfigureDeviceFeedback`
- size: `1129`
- prototype: `__int64 __fastcall(struct RIMDEV *)`
- caller_count: `4`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1400b1d68`
- `0x1401d0234`
- `0x140211e60`
- `0x140211ec4`

## callees

- `0x140049df8`
- `0x140049ec0`
- `0x14007b930`
- `0x14007efd0`
- `0x1400b234c`
- `0x1400b2540`
- `0x140156b2c`
- `0x1401610f8`
- `0x14019146c`
- `0x140200ac0`
- `0x140238a40`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140200e52`
- `ntoskrnl!ZwClose` at `0x140200e52`
- `ntoskrnl!KeInitializeEvent` at `0x140200c88`
- `ntoskrnl!KeInitializeEvent` at `0x140200c88`
- `ntoskrnl!KeWaitForSingleObject` at `0x140200ddf`
- `ntoskrnl!KeWaitForSingleObject` at `0x140200ddf`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140200cd2`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140200cd2`
- `ntoskrnl!IofCallDriver` at `0x140200db4`
- `ntoskrnl!IofCallDriver` at `0x140200db4`
- `ntoskrnl!ObfDereferenceObject` at `0x140200e42`
- `ntoskrnl!ObfDereferenceObject` at `0x140200e42`
- `WIN32K!W32GetUserSessionState` at `0x140200b37`
- `WIN32K!W32GetUserSessionState` at `0x140200d2f`
- `WIN32K!W32GetUserSessionState` at `0x140200ec6`
- `WIN32K!W32GetUserSessionState` at `0x140200b37`
- `WIN32K!W32GetUserSessionState` at `0x140200d2f`
- `WIN32K!W32GetUserSessionState` at `0x140200ec6`
- `HIDPARSE!HidP_SetUsageValue` at `0x140200c16`
- `HIDPARSE!HidP_SetUsageValue` at `0x140200c16`
- `HAL!KeQueryPerformanceCounter` at `0x140200df3`
- `HAL!KeQueryPerformanceCounter` at `0x140200df3`

## string_xrefs

- `0x140200d99`: `ConfigDeviceFeedback`

## pseudocode

```c

```
