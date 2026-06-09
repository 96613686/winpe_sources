# VhdmpiProcessEventComplete

- ea: `0x1400149f0`
- end: `0x140014aef`
- name: `VhdmpiProcessEventComplete`
- size: `255`
- prototype: `__int64 __fastcall(PEX_RUNDOWN_REF RunRef)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140010fa0`
- `0x140034e1c`
- `0x14004a85c`
- `0x1400b4470`

## callees

- `0x1400149f0`
- `0x1400261f0`
- `0x14002fdec`
- `0x140030178`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x140014a87`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140014a87`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014a1c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014a1c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014a5f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014a5f`

## pseudocode

```c

```
