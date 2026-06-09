# VhdmpStartIo

- ea: `0x1400178a0`
- end: `0x140017daf`
- name: `VhdmpStartIo`
- size: `1295`
- prototype: `__int64 __fastcall(struct _VHD_ADAPTER_EXTENSION *, struct _SCSI_REQUEST_BLOCK *)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting`

## callees

- `0x14000d080`
- `0x1400122b0`
- `0x1400178a0`
- `0x140018f90`
- `0x14001b830`
- `0x140023560`
- `0x140035bbc`
- `0x140035e94`
- `0x140046de8`
- `0x140047530`
- `0x140047858`
- `0x14005dd00`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x14001793d`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14001793d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017b11`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017b11`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017b34`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017b34`
- `storport!StorPortExtendedFunction` at `0x1400178eb`
- `storport!StorPortExtendedFunction` at `0x140017ad3`
- `storport!StorPortExtendedFunction` at `0x140017b62`
- `storport!StorPortExtendedFunction` at `0x1400178eb`
- `storport!StorPortExtendedFunction` at `0x140017ad3`
- `storport!StorPortExtendedFunction` at `0x140017b62`
- `storport!StorPortNotification` at `0x140017d91`
- `storport!StorPortNotification` at `0x140017d91`

## pseudocode

```c

```
