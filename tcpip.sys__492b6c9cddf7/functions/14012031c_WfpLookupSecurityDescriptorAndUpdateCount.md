# WfpLookupSecurityDescriptorAndUpdateCount

- ea: `0x14012031c`
- end: `0x140120746`
- name: `WfpLookupSecurityDescriptorAndUpdateCount`
- size: `1066`
- prototype: `__int64 __fastcall(PEPROCESS Process)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400bddc4`
- `0x140174d40`

## callees

- `0x14001b280`
- `0x140055780`
- `0x1400569e0`
- `0x1400996a0`
- `0x1400baa80`
- `0x1400bdc90`
- `0x14012031c`
- `0x14012074c`
- `0x140150fdc`
- `0x140174cb0`
- `0x1401bf390`
- `0x1401bf640`
- `0x1401bf940`
- `0x1401bfe60`

## import_xrefs

- `ntoskrnl!SeReleaseSubjectContext` at `0x1401206a9`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1401206a9`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140120699`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140120699`
- `ntoskrnl!SeLockSubjectContext` at `0x1401203f2`
- `ntoskrnl!SeLockSubjectContext` at `0x1401203f2`
- `ntoskrnl!SeCaptureSubjectContextEx` at `0x1401203e2`
- `ntoskrnl!SeCaptureSubjectContextEx` at `0x1401203e2`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140120655`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140120655`
- `ntoskrnl!SeSrpAccessCheck` at `0x140120547`
- `ntoskrnl!SeSrpAccessCheck` at `0x140120547`
- `NDIS!NdisReleaseRWLock` at `0x140120689`
- `NDIS!NdisReleaseRWLock` at `0x140120689`

## pseudocode

```c

```
