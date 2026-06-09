# VmsVmNicChannelDeleteChannel

- ea: `0x140194c4c`
- end: `0x140194eb2`
- name: `VmsVmNicChannelDeleteChannel`
- size: `614`
- prototype: ``
- caller_count: `8`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x14008b7e0`
- `0x140194118`
- `0x140194610`
- `0x140194aa4`
- `0x1401a5c10`
- `0x1401a6220`
- `0x1401a6da0`
- `0x1401a70c0`

## callees

- `0x140027a64`
- `0x14003a450`
- `0x14008497c`
- `0x1400867a0`
- `0x1400e6e60`
- `0x140194c4c`
- `0x1401a887c`

## import_xrefs

- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140194cb2`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140194cb2`
- `vmbkmclr!VmbChannelCleanup` at `0x140194e1c`
- `vmbkmclr!VmbChannelCleanup` at `0x140194e1c`
- `vmbkmclr!VmbChannelDisable` at `0x140194cc1`
- `vmbkmclr!VmbChannelDisable` at `0x140194cc1`
- `vmbkmclr!VmbChannelGetServicingState` at `0x140194d46`
- `vmbkmclr!VmbChannelGetServicingState` at `0x140194d99`
- `vmbkmclr!VmbChannelGetServicingState` at `0x140194df9`
- `vmbkmclr!VmbChannelGetServicingState` at `0x140194d46`
- `vmbkmclr!VmbChannelGetServicingState` at `0x140194d99`
- `vmbkmclr!VmbChannelGetServicingState` at `0x140194df9`

## string_xrefs

- `0x140194d11`: `ChannelState->IsAllocated && ChannelState->IsOpened == 0`

## pseudocode

```c

```
