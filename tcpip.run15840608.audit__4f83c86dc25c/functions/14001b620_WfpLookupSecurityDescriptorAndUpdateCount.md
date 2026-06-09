# WfpLookupSecurityDescriptorAndUpdateCount

- ea: `0x14001b620`
- end: `0x14001ba4a`
- name: `WfpLookupSecurityDescriptorAndUpdateCount`
- size: `1066`
- prototype: `__int64 __fastcall(PEPROCESS Process)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400c7514`
- `0x140176a40`

## callees

- `0x1400162f0`
- `0x140017630`
- `0x140019940`
- `0x14001b620`
- `0x14001ba50`
- `0x1400a1330`
- `0x1400c41d0`
- `0x1400c73e0`
- `0x140152ec8`
- `0x1401769b0`
- `0x1401c0fd0`
- `0x1401c1280`
- `0x1401c1580`
- `0x1401c1aa0`

## import_xrefs

- `ntoskrnl!SeReleaseSubjectContext` at `0x14001b9ad`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14001b9ad`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14001b99d`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14001b99d`
- `ntoskrnl!SeLockSubjectContext` at `0x14001b6f6`
- `ntoskrnl!SeLockSubjectContext` at `0x14001b6f6`
- `ntoskrnl!SeCaptureSubjectContextEx` at `0x14001b6e6`
- `ntoskrnl!SeCaptureSubjectContextEx` at `0x14001b6e6`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001b959`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001b959`
- `ntoskrnl!SeSrpAccessCheck` at `0x14001b84b`
- `ntoskrnl!SeSrpAccessCheck` at `0x14001b84b`
- `NDIS!NdisReleaseRWLock` at `0x14001b98d`
- `NDIS!NdisReleaseRWLock` at `0x14001b98d`

## pseudocode

```c

```
