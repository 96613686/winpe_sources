# VsmmDmSlpWaitForTransientMbpOperationComplete

- ea: `0x1400081d4`
- end: `0x14000849f`
- name: `VsmmDmSlpWaitForTransientMbpOperationComplete`
- size: `715`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140039428`

## callees

- `0x1400081d4`
- `0x14001fed8`
- `0x140021650`
- `0x140021800`
- `0x1400303c0`
- `0x140030760`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140008450`
- `ntoskrnl!KeSetEvent` at `0x140008450`
- `ntoskrnl!KeInitializeEvent` at `0x1400082df`
- `ntoskrnl!KeInitializeEvent` at `0x1400082df`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14000838a`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140008401`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14000838a`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140008401`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14000823c`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14000823c`

## pseudocode

```c

```
