# CCritSec::~CCritSec(void)

- ea: `0x180024f90`
- end: `0x180024fa0`
- name: `??1CCritSec@@QEAA@XZ`
- size: `16`
- prototype: `void __fastcall(CCritSec *__hidden this)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x18004483a`
- `0x1800448f8`
- `0x180044932`
- `0x18004495a`
- `0x1800449c4`
- `0x1800457a4`
- `0x180045f60`
- `0x18004607a`
- `0x1800460a6`
- `0x180046668`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180024f94`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180024f94`

## pseudocode

```c
void __fastcall CCritSec::~CCritSec(struct _RTL_CRITICAL_SECTION *this)
{
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x180024f90  sub     rsp, 28h
0x180024f94  call    cs:__imp_DeleteCriticalSection
0x180024f9a  nop
0x180024f9b  add     rsp, 28h
0x180024f9f  retn
```
