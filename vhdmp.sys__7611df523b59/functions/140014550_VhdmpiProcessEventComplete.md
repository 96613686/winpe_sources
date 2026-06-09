# VhdmpiProcessEventComplete

- ea: `0x140014550`
- end: `0x14001464f`
- name: `VhdmpiProcessEventComplete`
- size: `255`
- prototype: `__int64 __fastcall(PEX_RUNDOWN_REF RunRef)`
- caller_count: `6`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000fbf0`
- `0x140034728`
- `0x140034a2c`
- `0x14004a46c`
- `0x1400b4470`
- `0x1400b6c30`

## callees

- `0x140014550`
- `0x140025dd0`
- `0x14002f92c`
- `0x14002fcb8`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x1400145e7`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400145e7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001457c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001457c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400145bf`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400145bf`

## pseudocode

```c

```
