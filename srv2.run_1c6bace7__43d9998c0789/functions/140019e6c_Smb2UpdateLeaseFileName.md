# Smb2UpdateLeaseFileName

- ea: `0x140019e6c`
- end: `0x140019fa8`
- name: `Smb2UpdateLeaseFileName`
- size: `316`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140079130`
- `0x1400792e0`

## callees

- `0x140019e6c`
- `0x140038680`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140019f84`
- `ntoskrnl!ExAllocatePool2` at `0x140019f84`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019ee7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019ee7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019f21`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019f21`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003d37d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003d37d`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x140019ec1`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x140019ec1`

## pseudocode

```c

```
