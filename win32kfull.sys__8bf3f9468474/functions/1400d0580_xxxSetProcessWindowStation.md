# xxxSetProcessWindowStation

- ea: `0x1400d0580`
- end: `0x1400d0a3b`
- name: `xxxSetProcessWindowStation`
- size: `1211`
- prototype: `__int64 __fastcall(HANDLE SourceHandle)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400d04b0`

## callees

- `0x14000cd90`
- `0x140028660`
- `0x1400381a8`
- `0x140077cc8`
- `0x1400bcaa0`
- `0x1400c2a10`
- `0x1400d0580`
- `0x1400d0a70`
- `0x140297418`

## import_xrefs

- `ntoskrnl!PsSetProcessWindowStation` at `0x1400d09c2`
- `ntoskrnl!PsSetProcessWindowStation` at `0x1400d09d8`
- `ntoskrnl!PsSetProcessWindowStation` at `0x1400d0a2a`
- `ntoskrnl!PsSetProcessWindowStation` at `0x1400d09c2`
- `ntoskrnl!PsSetProcessWindowStation` at `0x1400d09d8`
- `ntoskrnl!PsSetProcessWindowStation` at `0x1400d0a2a`
- `ntoskrnl!PsGetProcessWin32WindowStation` at `0x1400d06b8`
- `ntoskrnl!PsGetProcessWin32WindowStation` at `0x1400d06d3`
- `ntoskrnl!PsGetProcessWin32WindowStation` at `0x1400d06b8`
- `ntoskrnl!PsGetProcessWin32WindowStation` at `0x1400d06d3`
- `ntoskrnl!PsGetThreadProcess` at `0x1400d05c8`
- `ntoskrnl!PsGetThreadProcess` at `0x1400d05c8`
- `ntoskrnl!ZwDuplicateObject` at `0x1400d0a0f`
- `ntoskrnl!ZwDuplicateObject` at `0x1400d0a0f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400d061f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400d0856`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400d061f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400d0856`
- `ntoskrnl!RtlAreAllAccessesGranted` at `0x1400d0711`
- `ntoskrnl!RtlAreAllAccessesGranted` at `0x1400d0711`
- `ntoskrnl!ObCloseHandle` at `0x1400d09b1`
- `ntoskrnl!ObCloseHandle` at `0x1400d09b1`
- `ntoskrnl!ExWindowStationObjectType` at `0x1400d05f7`
- `ntoskrnl!ExWindowStationObjectType` at `0x1400d082a`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400d05ab`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400d05ab`
- `ntoskrnl!ObfDereferenceObject` at `0x1400d0878`
- `ntoskrnl!ObfDereferenceObject` at `0x1400d0878`
- `ntoskrnl!PsGetProcessWin32Process` at `0x1400d05d7`
- `ntoskrnl!PsGetProcessWin32Process` at `0x1400d05d7`
- `win32kbase!LockObjectAssignment` at `0x1400d0699`
- `win32kbase!LockObjectAssignment` at `0x1400d0699`
- `win32kbase!UserDereferenceObject` at `0x1400d0654`
- `win32kbase!SetHandleFlag` at `0x1400d07ef`
- `win32kbase!SetHandleFlag` at `0x1400d0819`
- `win32kbase!SetHandleFlag` at `0x1400d07ef`
- `win32kbase!SetHandleFlag` at `0x1400d0819`
- `win32kbase!HMAssignmentUnlock` at `0x1400d08c1`
- `win32kbase!HMAssignmentUnlock` at `0x1400d090a`
- `win32kbase!HMAssignmentUnlock` at `0x1400d0955`
- `win32kbase!HMAssignmentUnlock` at `0x1400d0987`
- `win32kbase!HMAssignmentUnlock` at `0x1400d08c1`
- `win32kbase!HMAssignmentUnlock` at `0x1400d090a`
- `win32kbase!HMAssignmentUnlock` at `0x1400d0955`
- `win32kbase!HMAssignmentUnlock` at `0x1400d0987`

## pseudocode

```c

```
