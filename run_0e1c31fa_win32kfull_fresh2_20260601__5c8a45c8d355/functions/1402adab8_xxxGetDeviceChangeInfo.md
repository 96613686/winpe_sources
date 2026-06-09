# xxxGetDeviceChangeInfo

- ea: `0x1402adab8`
- end: `0x1402add3e`
- name: `xxxGetDeviceChangeInfo`
- size: `646`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path`

## callers

- `0x1402bb3e0`

## callees

- `0x1400b8c90`
- `0x1400e2cb0`
- `0x1400e8f88`
- `0x14013eb50`
- `0x1402a71e8`
- `0x1402adab8`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x1402adcbc`
- `ntoskrnl!IofCallDriver` at `0x1402adcbc`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1402adc98`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1402adc98`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x1402adc04`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x1402adc04`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x1402adb96`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x1402adb96`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x1402adb2a`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x1402adb2a`
- `ntoskrnl!KeInitializeEvent` at `0x1402adc4f`
- `ntoskrnl!KeInitializeEvent` at `0x1402adc4f`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402adce2`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402adce2`
- `ntoskrnl!PsGetCurrentProcess` at `0x1402adb02`
- `ntoskrnl!PsGetCurrentProcess` at `0x1402adb02`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402adbe7`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402adbe7`
- `win32kbase!UserDereferenceObject` at `0x1402adc40`
- `win32kbase!Win32FreePool` at `0x1402adbd8`
- `WIN32K!W32GetUserGdiSessionState` at `0x1402adaf2`
- `WIN32K!W32GetUserGdiSessionState` at `0x1402adaf2`
- `WIN32K!W32GetUserSessionState` at `0x1402adb17`
- `WIN32K!W32GetUserSessionState` at `0x1402adb36`
- `WIN32K!W32GetUserSessionState` at `0x1402adb4d`
- `WIN32K!W32GetUserSessionState` at `0x1402adb83`
- `WIN32K!W32GetUserSessionState` at `0x1402adb17`
- `WIN32K!W32GetUserSessionState` at `0x1402adb36`
- `WIN32K!W32GetUserSessionState` at `0x1402adb4d`
- `WIN32K!W32GetUserSessionState` at `0x1402adb83`

## string_xrefs

- `0x1402adbb7`: `\Device\MountPointManager`

## pseudocode

```c

```
