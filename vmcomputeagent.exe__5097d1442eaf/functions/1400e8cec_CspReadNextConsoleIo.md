# CspReadNextConsoleIo

- ea: `0x1400e8cec`
- end: `0x1400e8de1`
- name: `CspReadNextConsoleIo`
- size: `245`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400e0b10`
- `0x1400e8810`

## callees

- `0x1400e8cec`
- `0x1400e8e84`
- `0x1400fe010`

## import_xrefs

- `ntdll!TpCancelAsyncIoOperation` at `0x1400e8d93`
- `ntdll!TpCancelAsyncIoOperation` at `0x1400e8d93`
- `ntdll!TpStartAsyncIoOperation` at `0x1400e8d32`
- `ntdll!TpStartAsyncIoOperation` at `0x1400e8d32`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400e8daf`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400e8dcb`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400e8daf`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400e8dcb`
- `ntdll!RtlAcquireSRWLockShared` at `0x1400e8d05`
- `ntdll!RtlAcquireSRWLockShared` at `0x1400e8d05`
- `ntdll!NtDeviceIoControlFile` at `0x1400e8d83`
- `ntdll!NtDeviceIoControlFile` at `0x1400e8d83`

## pseudocode

```c

```
