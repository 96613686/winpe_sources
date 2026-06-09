# VhdmpiDeclareVirtualDiskInvalid

- ea: `0x140033648`
- end: `0x1400337c8`
- name: `VhdmpiDeclareVirtualDiskInvalid`
- size: `384`
- prototype: `__int64 __fastcall(char)`
- caller_count: `4`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400078f0`
- `0x140015918`
- `0x1400186b4`
- `0x1400cded0`

## callees

- `0x140016820`
- `0x140023560`
- `0x1400269cc`
- `0x1400333a0`
- `0x140033514`
- `0x140033648`
- `0x140033fbc`
- `0x140035e94`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14003367d`
- `ntoskrnl!KeBugCheckEx` at `0x14003367d`
- `ntoskrnl!KeSetEvent` at `0x14003379e`
- `ntoskrnl!KeSetEvent` at `0x14003379e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003377a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003377a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400337b0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400337b0`

## string_xrefs

- `0x1400336c2`: `Virtual disk becoming invalid VirtualDisk=0x%p 0x%08x`

## pseudocode

```c

```
