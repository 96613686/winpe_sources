# VmsPDSwitchDataPathModeUnsafe

- ea: `0x14012cb8c`
- end: `0x14012cf94`
- name: `VmsPDSwitchDataPathModeUnsafe`
- size: `1032`
- prototype: ``
- caller_count: `5`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400b31a4`
- `0x14010177c`
- `0x14012b960`
- `0x140138df8`
- `0x14013aed4`

## callees

- `0x140027a64`
- `0x14002e45c`
- `0x1400667f4`
- `0x14006b084`
- `0x14007ad50`
- `0x14008497c`
- `0x1400a0ef8`
- `0x1400a2060`
- `0x1400ed3e0`
- `0x14012b0c0`
- `0x14012ba28`
- `0x14012c614`
- `0x14012cb8c`
- `0x1401bbc40`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x14012cf2c`
- `ntoskrnl!KeReleaseMutex` at `0x14012cf2c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14012cc84`
- `ntoskrnl!KeWaitForSingleObject` at `0x14012cc84`
- `NDIS!NdisConvertNdisStatusToNtStatus` at `0x14012cc17`
- `NDIS!NdisConvertNdisStatusToNtStatus` at `0x14012cf14`
- `NDIS!NdisConvertNdisStatusToNtStatus` at `0x14012cc17`
- `NDIS!NdisConvertNdisStatusToNtStatus` at `0x14012cf14`
- `NDIS!NdisReleaseRWLock` at `0x14012ceca`
- `NDIS!NdisReleaseRWLock` at `0x14012ceca`

## string_xrefs

- `0x14012cc42`: `ObjSwitch->ExtensionStack.ProtocolState == VmsExtPtStatePaused`

## pseudocode

```c

```
