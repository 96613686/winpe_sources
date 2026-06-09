# SP_POOL::CommitDevices(_SP_DEVICE_CHANGE *,ulong)

- ea: `0x1400320a8`
- end: `0x140032293`
- name: `?CommitDevices@SP_POOL@@AEAAXPEAU_SP_DEVICE_CHANGE@@K@Z`
- size: `491`
- prototype: `void __fastcall(SP_POOL *__hidden this, struct _SP_DEVICE_CHANGE *, unsigned int)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14009d930`
- `0x14009e404`
- `0x1400a0f3c`

## callees

- `0x14002b094`
- `0x14002bc90`
- `0x1400320a8`
- `0x14003b1b8`
- `0x14003c6c4`
- `0x140043250`
- `0x14009cfb4`
- `0x1400a4fd4`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003211e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003211e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140032158`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140032158`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x1400321ca`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x140032279`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x1400321ca`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x140032279`

## pseudocode

```c

```
