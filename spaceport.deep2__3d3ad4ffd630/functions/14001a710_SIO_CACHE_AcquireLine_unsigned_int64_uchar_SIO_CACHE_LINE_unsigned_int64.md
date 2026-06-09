# SIO_CACHE::AcquireLine(unsigned __int64,uchar,SIO_CACHE_LINE * *,unsigned __int64 *)

- ea: `0x14001a710`
- end: `0x14001a877`
- name: `?AcquireLine@SIO_CACHE@@IEAAJ_KEPEAPEAVSIO_CACHE_LINE@@PEA_K@Z`
- size: `359`
- prototype: `__int64 __fastcall(SIO_CACHE *__hidden this, unsigned __int64, unsigned __int8, struct SIO_CACHE_LINE **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14004829c`

## callees

- `0x14000ec40`
- `0x14001a710`
- `0x140026b40`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockShared` at `0x14001a7bb`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x14001a7bb`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x14001a73f`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x14001a73f`

## pseudocode

```c

```
