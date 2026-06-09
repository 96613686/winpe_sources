# TcpCloseEndpointWorkQueueRoutine

- ea: `0x14003a900`
- end: `0x14003ac0f`
- name: `TcpCloseEndpointWorkQueueRoutine`
- size: `783`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x14003a730`
- `0x14003bab0`

## callees

- `0x140039590`
- `0x14003a900`
- `0x140060240`
- `0x140060360`
- `0x1400606a4`
- `0x1400a3050`
- `0x1400a3320`
- `0x1400e702c`
- `0x140166cec`
- `0x1401bf4d0`

## import_xrefs

- `ntoskrnl!KeBugCheck` at `0x14003aba4`
- `ntoskrnl!KeBugCheck` at `0x14003aba4`
- `ntoskrnl!PsGetCurrentThreadProcessId` at `0x14003a9bf`
- `ntoskrnl!PsGetCurrentThreadProcessId` at `0x14003a9bf`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14003a9ce`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14003a9ce`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14003a9ee`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14003a9ee`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14003aaaa`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14003aaaa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003aae2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003aae2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003aad6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003aad6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003aa99`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003aa99`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003aa03`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003aa03`
- `NETIO!NetioInsertWorkQueue` at `0x14003abbb`
- `NETIO!NetioInsertWorkQueue` at `0x14003abbb`

## pseudocode

```c

```
