# xxxGetDeviceChangeInfo

- ea: `0x1402ab678`
- end: `0x1402ab8fe`
- name: `xxxGetDeviceChangeInfo`
- size: `646`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path`

## callers

- `0x1402b96d0`

## callees

- `0x1400bcaa0`
- `0x1400c2dd8`
- `0x1400d0a70`
- `0x140148b90`
- `0x1402a4da8`
- `0x1402ab678`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x1402ab87c`
- `ntoskrnl!IofCallDriver` at `0x1402ab87c`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1402ab858`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1402ab858`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x1402ab7c4`
- `ntoskrnl!IoGetDeviceObjectPointer` at `0x1402ab7c4`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x1402ab756`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x1402ab756`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x1402ab6ea`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x1402ab6ea`
- `ntoskrnl!KeInitializeEvent` at `0x1402ab80f`
- `ntoskrnl!KeInitializeEvent` at `0x1402ab80f`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402ab8a2`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402ab8a2`
- `ntoskrnl!PsGetCurrentProcess` at `0x1402ab6c2`
- `ntoskrnl!PsGetCurrentProcess` at `0x1402ab6c2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402ab7a7`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402ab7a7`
- `win32kbase!UserDereferenceObject` at `0x1402ab800`
- `win32kbase!Win32FreePool` at `0x1402ab798`
- `WIN32K!W32GetUserGdiSessionState` at `0x1402ab6b2`
- `WIN32K!W32GetUserGdiSessionState` at `0x1402ab6b2`
- `WIN32K!W32GetUserSessionState` at `0x1402ab6d7`
- `WIN32K!W32GetUserSessionState` at `0x1402ab6f6`
- `WIN32K!W32GetUserSessionState` at `0x1402ab70d`
- `WIN32K!W32GetUserSessionState` at `0x1402ab743`
- `WIN32K!W32GetUserSessionState` at `0x1402ab6d7`
- `WIN32K!W32GetUserSessionState` at `0x1402ab6f6`
- `WIN32K!W32GetUserSessionState` at `0x1402ab70d`
- `WIN32K!W32GetUserSessionState` at `0x1402ab743`

## string_xrefs

- `0x1402ab777`: `\Device\MountPointManager`

## pseudocode

```c

```
