# VhdmpStartIo

- ea: `0x140017d40`
- end: `0x14001824f`
- name: `VhdmpStartIo`
- size: `1295`
- prototype: `__int64 __fastcall(struct _VHD_ADAPTER_EXTENSION *, struct _SCSI_REQUEST_BLOCK *)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting`

## callees

- `0x14000d680`
- `0x14000fd30`
- `0x140017d40`
- `0x140019430`
- `0x14001bc50`
- `0x140023980`
- `0x140035fac`
- `0x140036284`
- `0x1400471d8`
- `0x140047920`
- `0x140047c48`
- `0x14005e100`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x140017ddd`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140017ddd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017fb1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140017fb1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017fd4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140017fd4`
- `storport!StorPortExtendedFunction` at `0x140017d8b`
- `storport!StorPortExtendedFunction` at `0x140017f73`
- `storport!StorPortExtendedFunction` at `0x140018002`
- `storport!StorPortExtendedFunction` at `0x140017d8b`
- `storport!StorPortExtendedFunction` at `0x140017f73`
- `storport!StorPortExtendedFunction` at `0x140018002`
- `storport!StorPortNotification` at `0x140018231`
- `storport!StorPortNotification` at `0x140018231`

## pseudocode

```c

```
