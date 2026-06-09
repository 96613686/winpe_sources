# SIO_RAID5::UpdateBitMap(unsigned __int64,unsigned __int64,uchar)

- ea: `0x140051768`
- end: `0x14005188c`
- name: `?UpdateBitMap@SIO_RAID5@@QEAAJ_K0E@Z`
- size: `292`
- prototype: `__int64 __fastcall(SIO_RAID5 *__hidden this, unsigned __int64, unsigned __int64, unsigned __int8)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1400133c0`

## callees

- `0x140009c20`
- `0x14000acc0`
- `0x140027040`
- `0x14002b024`
- `0x140051768`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14005186c`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14005186c`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400517bc`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400517bc`
- `ntoskrnl!RtlSetBit` at `0x140051816`
- `ntoskrnl!RtlSetBit` at `0x140051816`

## pseudocode

```c

```
