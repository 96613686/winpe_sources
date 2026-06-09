# WfpLookupSecurityDescriptorAndUpdateCount

- ea: `0x14012045c`
- end: `0x140120886`
- name: `WfpLookupSecurityDescriptorAndUpdateCount`
- size: `1066`
- prototype: `__int64 __fastcall(PEPROCESS Process)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400bddf4`
- `0x140174e80`

## callees

- `0x14001b520`
- `0x140055a20`
- `0x140056c80`
- `0x14009a550`
- `0x1400ba6a0`
- `0x1400bdcc0`
- `0x14012045c`
- `0x14012088c`
- `0x14015111c`
- `0x140174df0`
- `0x1401bf4d0`
- `0x1401bf780`
- `0x1401bfa80`
- `0x1401bffa0`

## import_xrefs

- `ntoskrnl!SeReleaseSubjectContext` at `0x1401207e9`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1401207e9`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1401207d9`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1401207d9`
- `ntoskrnl!SeLockSubjectContext` at `0x140120532`
- `ntoskrnl!SeLockSubjectContext` at `0x140120532`
- `ntoskrnl!SeCaptureSubjectContextEx` at `0x140120522`
- `ntoskrnl!SeCaptureSubjectContextEx` at `0x140120522`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140120795`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140120795`
- `ntoskrnl!SeSrpAccessCheck` at `0x140120687`
- `ntoskrnl!SeSrpAccessCheck` at `0x140120687`
- `NDIS!NdisReleaseRWLock` at `0x1401207c9`
- `NDIS!NdisReleaseRWLock` at `0x1401207c9`

## pseudocode

```c

```
