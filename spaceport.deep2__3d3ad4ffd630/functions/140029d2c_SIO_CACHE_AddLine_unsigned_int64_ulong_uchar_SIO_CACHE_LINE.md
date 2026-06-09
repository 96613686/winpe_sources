# SIO_CACHE::AddLine(unsigned __int64,ulong,uchar,SIO_CACHE_LINE * *)

- ea: `0x140029d2c`
- end: `0x140029edc`
- name: `?AddLine@SIO_CACHE@@IEAAJ_KKEPEAPEAVSIO_CACHE_LINE@@@Z`
- size: `432`
- prototype: `__int64 __usercall@<rax>(SIO_CACHE *__hidden this@<rcx>, unsigned __int64@<rdx>, unsigned int@<r8d>, unsigned __int8@<r9b>, struct SIO_CACHE_LINE **)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14004845c`

## callees

- `0x140019b10`
- `0x14001a250`
- `0x14001ece0`
- `0x140025800`
- `0x140025df0`
- `0x140029d2c`
- `0x14002a03c`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140029ea7`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140029ea7`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140029d65`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140029d65`
- `ntoskrnl!RtlSetBit` at `0x140029e1a`
- `ntoskrnl!RtlSetBit` at `0x140029e1a`

## pseudocode

```c

```
