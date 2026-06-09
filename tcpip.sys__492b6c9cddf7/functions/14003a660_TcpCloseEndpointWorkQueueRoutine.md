# TcpCloseEndpointWorkQueueRoutine

- ea: `0x14003a660`
- end: `0x14003a96f`
- name: `TcpCloseEndpointWorkQueueRoutine`
- size: `783`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x14003a490`
- `0x14003b810`

## callees

- `0x1400392f0`
- `0x14003a660`
- `0x14005ffa0`
- `0x1400600c0`
- `0x140060404`
- `0x1400a2180`
- `0x1400a2450`
- `0x1400e713c`
- `0x140166bac`
- `0x1401bf390`

## import_xrefs

- `ntoskrnl!KeBugCheck` at `0x14003a904`
- `ntoskrnl!KeBugCheck` at `0x14003a904`
- `ntoskrnl!PsGetCurrentThreadProcessId` at `0x14003a71f`
- `ntoskrnl!PsGetCurrentThreadProcessId` at `0x14003a71f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14003a72e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14003a72e`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14003a74e`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14003a74e`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14003a80a`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14003a80a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003a842`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003a842`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003a836`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003a836`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003a7f9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003a7f9`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003a763`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003a763`
- `NETIO!NetioInsertWorkQueue` at `0x14003a91b`
- `NETIO!NetioInsertWorkQueue` at `0x14003a91b`

## pseudocode

```c

```
