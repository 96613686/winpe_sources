# RaUnitIncrementOutstandingIrpRequests

- ea: `0x1400022bc`
- end: `0x140002439`
- name: `RaUnitIncrementOutstandingIrpRequests`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400021a0`

## callees

- `0x140001710`
- `0x1400018b0`
- `0x1400022bc`
- `0x1400172d0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140002421`
- `ntoskrnl!KeReleaseSpinLock` at `0x14014bec3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14014bef7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002421`
- `ntoskrnl!KeReleaseSpinLock` at `0x14014bec3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14014bef7`
- `ntoskrnl!IoQueueWorkItem` at `0x14014bf40`
- `ntoskrnl!IoQueueWorkItem` at `0x14014bf40`
- `ntoskrnl!IofCompleteRequest` at `0x14000240c`
- `ntoskrnl!IofCompleteRequest` at `0x14000240c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14014be94`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14014bf66`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14014be94`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14014bf66`

## pseudocode

```c

```
