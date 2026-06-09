# VmsPDSwitchDataPathModeUnsafe

- ea: `0x14012cbfc`
- end: `0x14012d004`
- name: `VmsPDSwitchDataPathModeUnsafe`
- size: `1032`
- prototype: ``
- caller_count: `5`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400b3214`
- `0x1401017ec`
- `0x14012b9d0`
- `0x140138e68`
- `0x14013af44`

## callees

- `0x140027a64`
- `0x14002e45c`
- `0x1400667f4`
- `0x14006b084`
- `0x14007ad50`
- `0x14008497c`
- `0x1400a0ef8`
- `0x1400a2060`
- `0x1400ed450`
- `0x14012b130`
- `0x14012ba98`
- `0x14012c684`
- `0x14012cbfc`
- `0x1401bbcb0`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x14012cf9c`
- `ntoskrnl!KeReleaseMutex` at `0x14012cf9c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14012ccf4`
- `ntoskrnl!KeWaitForSingleObject` at `0x14012ccf4`
- `NDIS!NdisConvertNdisStatusToNtStatus` at `0x14012cc87`
- `NDIS!NdisConvertNdisStatusToNtStatus` at `0x14012cf84`
- `NDIS!NdisConvertNdisStatusToNtStatus` at `0x14012cc87`
- `NDIS!NdisConvertNdisStatusToNtStatus` at `0x14012cf84`
- `NDIS!NdisReleaseRWLock` at `0x14012cf3a`
- `NDIS!NdisReleaseRWLock` at `0x14012cf3a`

## string_xrefs

- `0x14012ccb2`: `ObjSwitch->ExtensionStack.ProtocolState == VmsExtPtStatePaused`

## pseudocode

```c

```
