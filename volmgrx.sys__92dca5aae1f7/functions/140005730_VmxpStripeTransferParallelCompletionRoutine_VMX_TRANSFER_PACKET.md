# VmxpStripeTransferParallelCompletionRoutine(VMX_TRANSFER_PACKET *)

- ea: `0x140005730`
- end: `0x14000585d`
- name: `?VmxpStripeTransferParallelCompletionRoutine@@YAXPEAVVMX_TRANSFER_PACKET@@@Z`
- size: `301`
- prototype: `void __fastcall(struct VMX_TRANSFER_PACKET *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140005730`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005763`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005763`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005805`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005805`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x14000579d`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x1400057bc`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x14000579d`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x1400057bc`

## pseudocode

```c

```
