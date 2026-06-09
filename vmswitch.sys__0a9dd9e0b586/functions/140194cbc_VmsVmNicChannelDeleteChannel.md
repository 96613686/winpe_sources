# VmsVmNicChannelDeleteChannel

- ea: `0x140194cbc`
- end: `0x140194f22`
- name: `VmsVmNicChannelDeleteChannel`
- size: `614`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x14008b7e0`
- `0x140194188`
- `0x140194680`
- `0x140194b14`
- `0x1401a5c80`
- `0x1401a6290`
- `0x1401a6e10`
- `0x1401a7130`

## callees

- `0x140027a64`
- `0x14003a450`
- `0x14008497c`
- `0x1400867a0`
- `0x1400e6ed0`
- `0x140194cbc`
- `0x1401a88ec`

## import_xrefs

- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140194d22`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140194d22`
- `vmbkmclr!VmbChannelCleanup` at `0x140194e8c`
- `vmbkmclr!VmbChannelCleanup` at `0x140194e8c`
- `vmbkmclr!VmbChannelDisable` at `0x140194d31`
- `vmbkmclr!VmbChannelDisable` at `0x140194d31`
- `vmbkmclr!VmbChannelGetServicingState` at `0x140194db6`
- `vmbkmclr!VmbChannelGetServicingState` at `0x140194e09`
- `vmbkmclr!VmbChannelGetServicingState` at `0x140194e69`
- `vmbkmclr!VmbChannelGetServicingState` at `0x140194db6`
- `vmbkmclr!VmbChannelGetServicingState` at `0x140194e09`
- `vmbkmclr!VmbChannelGetServicingState` at `0x140194e69`

## string_xrefs

- `0x140194d81`: `ChannelState->IsAllocated && ChannelState->IsOpened == 0`

## pseudocode

```c

```
