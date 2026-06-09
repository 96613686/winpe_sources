# RIMHidGetPreparsedData

- ea: `0x1400bc8b4`
- end: `0x1400bd0b7`
- name: `RIMHidGetPreparsedData`
- size: `2051`
- prototype: `__int64 __fastcall(int, int, int, int, PVOID)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path`

## callers

- `0x1400ba768`

## callees

- `0x14004a0d0`
- `0x14004d770`
- `0x1400729c8`
- `0x140072a90`
- `0x1400775c0`
- `0x1400bc8b4`
- `0x1400be4ec`
- `0x1400be6e0`
- `0x1401a9f9c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400bd067`
- `ntoskrnl!ZwClose` at `0x1400bd067`
- `ntoskrnl!ObfReferenceObject` at `0x1400bc934`
- `ntoskrnl!ObfReferenceObject` at `0x1400bc934`
- `ntoskrnl!KeInitializeEvent` at `0x1400bc991`
- `ntoskrnl!KeInitializeEvent` at `0x1400bcaf4`
- `ntoskrnl!KeInitializeEvent` at `0x1400bc991`
- `ntoskrnl!KeInitializeEvent` at `0x1400bcaf4`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400bca3f`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400bcba0`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400bca3f`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400bcba0`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400bc9d3`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400bcb34`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400bc9d3`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400bcb34`
- `ntoskrnl!IofCallDriver` at `0x1400bca14`
- `ntoskrnl!IofCallDriver` at `0x1400bcb75`
- `ntoskrnl!IofCallDriver` at `0x1400bca14`
- `ntoskrnl!IofCallDriver` at `0x1400bcb75`
- `ntoskrnl!ObfDereferenceObject` at `0x1400bd04d`
- `ntoskrnl!ObfDereferenceObject` at `0x1400bd09f`
- `ntoskrnl!ObfDereferenceObject` at `0x1400bd04d`
- `ntoskrnl!ObfDereferenceObject` at `0x1400bd09f`
- `WIN32K!W32GetUserSessionState` at `0x1400bcc18`
- `WIN32K!W32GetUserSessionState` at `0x1400bcc88`
- `WIN32K!W32GetUserSessionState` at `0x1400bcd40`
- `WIN32K!W32GetUserSessionState` at `0x1400bce06`
- `WIN32K!W32GetUserSessionState` at `0x1400bce2e`
- `WIN32K!W32GetUserSessionState` at `0x1400bceb0`
- `WIN32K!W32GetUserSessionState` at `0x1400bcf79`
- `WIN32K!W32GetUserSessionState` at `0x1400bcff4`
- `WIN32K!W32GetUserSessionState` at `0x1400bcc18`
- `WIN32K!W32GetUserSessionState` at `0x1400bcc88`
- `WIN32K!W32GetUserSessionState` at `0x1400bcd40`
- `WIN32K!W32GetUserSessionState` at `0x1400bce06`
- `WIN32K!W32GetUserSessionState` at `0x1400bce2e`
- `WIN32K!W32GetUserSessionState` at `0x1400bceb0`
- `WIN32K!W32GetUserSessionState` at `0x1400bcf79`
- `WIN32K!W32GetUserSessionState` at `0x1400bcff4`
- `HAL!KeQueryPerformanceCounter` at `0x1400bc9ff`
- `HAL!KeQueryPerformanceCounter` at `0x1400bca51`
- `HAL!KeQueryPerformanceCounter` at `0x1400bcb60`
- `HAL!KeQueryPerformanceCounter` at `0x1400bcbb2`
- `HAL!KeQueryPerformanceCounter` at `0x1400bc9ff`
- `HAL!KeQueryPerformanceCounter` at `0x1400bca51`
- `HAL!KeQueryPerformanceCounter` at `0x1400bcb60`
- `HAL!KeQueryPerformanceCounter` at `0x1400bcbb2`

## string_xrefs

- `0x1400bca6a`: `GetPreparsedData`
- `0x1400bcbcb`: `GetCollectionDescriptor`

## pseudocode

```c

```
