# SP_POOL::CommitDevices(_SP_DEVICE_CHANGE *,ulong)

- ea: `0x140032038`
- end: `0x140032223`
- name: `?CommitDevices@SP_POOL@@AEAAXPEAU_SP_DEVICE_CHANGE@@K@Z`
- size: `491`
- prototype: `void __fastcall(SP_POOL *__hidden this, struct _SP_DEVICE_CHANGE *, unsigned int)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14009d910`
- `0x14009e3e4`
- `0x1400a0e0c`

## callees

- `0x14002b094`
- `0x14002bc90`
- `0x140032038`
- `0x14003b0f8`
- `0x14003c604`
- `0x140043190`
- `0x14009cf94`
- `0x1400a4ea4`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400320ae`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400320ae`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400320e8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400320e8`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x14003215a`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x140032209`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x14003215a`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x140032209`

## pseudocode

```c

```
