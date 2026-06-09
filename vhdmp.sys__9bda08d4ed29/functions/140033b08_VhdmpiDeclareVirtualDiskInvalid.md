# VhdmpiDeclareVirtualDiskInvalid

- ea: `0x140033b08`
- end: `0x140033c88`
- name: `VhdmpiDeclareVirtualDiskInvalid`
- size: `384`
- prototype: `__int64 __fastcall(char)`
- caller_count: `4`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400078f0`
- `0x140015db8`
- `0x140018b54`
- `0x1400cde60`

## callees

- `0x140016cc0`
- `0x140023980`
- `0x140026dec`
- `0x140033860`
- `0x1400339d4`
- `0x140033b08`
- `0x14003447c`
- `0x140036284`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x140033b3d`
- `ntoskrnl!KeBugCheckEx` at `0x140033b3d`
- `ntoskrnl!KeSetEvent` at `0x140033c5e`
- `ntoskrnl!KeSetEvent` at `0x140033c5e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140033c3a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140033c3a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140033c70`
- `ntoskrnl!KeReleaseSpinLock` at `0x140033c70`

## string_xrefs

- `0x140033b82`: `Virtual disk becoming invalid VirtualDisk=0x%p 0x%08x`

## pseudocode

```c

```
