# CspReadNextConsoleIo

- ea: `0x14029e314`
- end: `0x14029e42e`
- name: `CspReadNextConsoleIo`
- size: `282`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140080ed8`
- `0x14029dff0`

## callees

- `0x14029e314`
- `0x14029e4d8`
- `0x1402c4010`

## import_xrefs

- `ntdll!RtlAcquireSRWLockShared` at `0x14029e32d`
- `ntdll!RtlAcquireSRWLockShared` at `0x14029e32d`
- `ntdll!RtlReleaseSRWLockShared` at `0x14029e3ef`
- `ntdll!RtlReleaseSRWLockShared` at `0x14029e411`
- `ntdll!RtlReleaseSRWLockShared` at `0x14029e3ef`
- `ntdll!RtlReleaseSRWLockShared` at `0x14029e411`
- `ntdll!TpStartAsyncIoOperation` at `0x14029e360`
- `ntdll!TpStartAsyncIoOperation` at `0x14029e360`
- `ntdll!TpCancelAsyncIoOperation` at `0x14029e3cd`
- `ntdll!TpCancelAsyncIoOperation` at `0x14029e3cd`
- `ntdll!NtDeviceIoControlFile` at `0x14029e3b7`
- `ntdll!NtDeviceIoControlFile` at `0x14029e3b7`

## pseudocode

```c

```
