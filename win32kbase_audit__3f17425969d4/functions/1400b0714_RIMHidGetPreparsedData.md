# RIMHidGetPreparsedData

- ea: `0x1400b0714`
- end: `0x1400b0f17`
- name: `RIMHidGetPreparsedData`
- size: `2051`
- prototype: `_DWORD *__fastcall(struct RIMDEV *, HANDLE *, PVOID *, PVOID *, _DWORD *OutputBuffer)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path`

## callers

- `0x1400ae5c8`

## callees

- `0x140049df8`
- `0x140049ec0`
- `0x14004e9f0`
- `0x14007b930`
- `0x14007efd0`
- `0x1400b0714`
- `0x1400b234c`
- `0x1400b2540`
- `0x1401aab9c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400b0ec7`
- `ntoskrnl!ZwClose` at `0x1400b0ec7`
- `ntoskrnl!ObfReferenceObject` at `0x1400b0794`
- `ntoskrnl!ObfReferenceObject` at `0x1400b0794`
- `ntoskrnl!KeInitializeEvent` at `0x1400b07f1`
- `ntoskrnl!KeInitializeEvent` at `0x1400b0954`
- `ntoskrnl!KeInitializeEvent` at `0x1400b07f1`
- `ntoskrnl!KeInitializeEvent` at `0x1400b0954`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400b089f`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400b0a00`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400b089f`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400b0a00`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400b0833`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400b0994`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400b0833`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400b0994`
- `ntoskrnl!IofCallDriver` at `0x1400b0874`
- `ntoskrnl!IofCallDriver` at `0x1400b09d5`
- `ntoskrnl!IofCallDriver` at `0x1400b0874`
- `ntoskrnl!IofCallDriver` at `0x1400b09d5`
- `ntoskrnl!ObfDereferenceObject` at `0x1400b0ead`
- `ntoskrnl!ObfDereferenceObject` at `0x1400b0eff`
- `ntoskrnl!ObfDereferenceObject` at `0x1400b0ead`
- `ntoskrnl!ObfDereferenceObject` at `0x1400b0eff`
- `WIN32K!W32GetUserSessionState` at `0x1400b0a78`
- `WIN32K!W32GetUserSessionState` at `0x1400b0ae8`
- `WIN32K!W32GetUserSessionState` at `0x1400b0ba0`
- `WIN32K!W32GetUserSessionState` at `0x1400b0c66`
- `WIN32K!W32GetUserSessionState` at `0x1400b0c8e`
- `WIN32K!W32GetUserSessionState` at `0x1400b0d10`
- `WIN32K!W32GetUserSessionState` at `0x1400b0dd9`
- `WIN32K!W32GetUserSessionState` at `0x1400b0e54`
- `WIN32K!W32GetUserSessionState` at `0x1400b0a78`
- `WIN32K!W32GetUserSessionState` at `0x1400b0ae8`
- `WIN32K!W32GetUserSessionState` at `0x1400b0ba0`
- `WIN32K!W32GetUserSessionState` at `0x1400b0c66`
- `WIN32K!W32GetUserSessionState` at `0x1400b0c8e`
- `WIN32K!W32GetUserSessionState` at `0x1400b0d10`
- `WIN32K!W32GetUserSessionState` at `0x1400b0dd9`
- `WIN32K!W32GetUserSessionState` at `0x1400b0e54`
- `HAL!KeQueryPerformanceCounter` at `0x1400b085f`
- `HAL!KeQueryPerformanceCounter` at `0x1400b08b1`
- `HAL!KeQueryPerformanceCounter` at `0x1400b09c0`
- `HAL!KeQueryPerformanceCounter` at `0x1400b0a12`
- `HAL!KeQueryPerformanceCounter` at `0x1400b085f`
- `HAL!KeQueryPerformanceCounter` at `0x1400b08b1`
- `HAL!KeQueryPerformanceCounter` at `0x1400b09c0`
- `HAL!KeQueryPerformanceCounter` at `0x1400b0a12`

## string_xrefs

- `0x1400b08ca`: `GetPreparsedData`
- `0x1400b0a2b`: `GetCollectionDescriptor`

## pseudocode

```c

```
