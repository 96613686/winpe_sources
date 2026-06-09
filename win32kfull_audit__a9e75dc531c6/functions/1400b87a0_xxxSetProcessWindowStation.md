# xxxSetProcessWindowStation

- ea: `0x1400b87a0`
- end: `0x1400b8c5b`
- name: `xxxSetProcessWindowStation`
- size: `1211`
- prototype: `__int64 __fastcall(HANDLE SourceHandle, KPROCESSOR_MODE, int)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400b86d0`

## callees

- `0x140023570`
- `0x140033b58`
- `0x1400a4a38`
- `0x1400b87a0`
- `0x1400b8c90`
- `0x1400d0e30`
- `0x1400e2cb0`
- `0x1400e8c20`
- `0x1402998f8`

## import_xrefs

- `ntoskrnl!PsSetProcessWindowStation` at `0x1400b8be2`
- `ntoskrnl!PsSetProcessWindowStation` at `0x1400b8bf8`
- `ntoskrnl!PsSetProcessWindowStation` at `0x1400b8c4a`
- `ntoskrnl!PsSetProcessWindowStation` at `0x1400b8be2`
- `ntoskrnl!PsSetProcessWindowStation` at `0x1400b8bf8`
- `ntoskrnl!PsSetProcessWindowStation` at `0x1400b8c4a`
- `ntoskrnl!PsGetProcessWin32WindowStation` at `0x1400b88d8`
- `ntoskrnl!PsGetProcessWin32WindowStation` at `0x1400b88f3`
- `ntoskrnl!PsGetProcessWin32WindowStation` at `0x1400b88d8`
- `ntoskrnl!PsGetProcessWin32WindowStation` at `0x1400b88f3`
- `ntoskrnl!PsGetThreadProcess` at `0x1400b87e8`
- `ntoskrnl!PsGetThreadProcess` at `0x1400b87e8`
- `ntoskrnl!ZwDuplicateObject` at `0x1400b8c2f`
- `ntoskrnl!ZwDuplicateObject` at `0x1400b8c2f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400b883f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400b8a76`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400b883f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400b8a76`
- `ntoskrnl!RtlAreAllAccessesGranted` at `0x1400b8931`
- `ntoskrnl!RtlAreAllAccessesGranted` at `0x1400b8931`
- `ntoskrnl!ObCloseHandle` at `0x1400b8bd1`
- `ntoskrnl!ObCloseHandle` at `0x1400b8bd1`
- `ntoskrnl!ExWindowStationObjectType` at `0x1400b8817`
- `ntoskrnl!ExWindowStationObjectType` at `0x1400b8a4a`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400b87cb`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400b87cb`
- `ntoskrnl!ObfDereferenceObject` at `0x1400b8a98`
- `ntoskrnl!ObfDereferenceObject` at `0x1400b8a98`
- `ntoskrnl!PsGetProcessWin32Process` at `0x1400b87f7`
- `ntoskrnl!PsGetProcessWin32Process` at `0x1400b87f7`
- `win32kbase!LockObjectAssignment` at `0x1400b88b9`
- `win32kbase!LockObjectAssignment` at `0x1400b88b9`
- `win32kbase!UserDereferenceObject` at `0x1400b8874`
- `win32kbase!SetHandleFlag` at `0x1400b8a0f`
- `win32kbase!SetHandleFlag` at `0x1400b8a39`
- `win32kbase!SetHandleFlag` at `0x1400b8a0f`
- `win32kbase!SetHandleFlag` at `0x1400b8a39`
- `win32kbase!HMAssignmentUnlock` at `0x1400b8ae1`
- `win32kbase!HMAssignmentUnlock` at `0x1400b8b2a`
- `win32kbase!HMAssignmentUnlock` at `0x1400b8b75`
- `win32kbase!HMAssignmentUnlock` at `0x1400b8ba7`
- `win32kbase!HMAssignmentUnlock` at `0x1400b8ae1`
- `win32kbase!HMAssignmentUnlock` at `0x1400b8b2a`
- `win32kbase!HMAssignmentUnlock` at `0x1400b8b75`
- `win32kbase!HMAssignmentUnlock` at `0x1400b8ba7`

## pseudocode

```c

```
