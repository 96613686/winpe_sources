# CCritSec::~CCritSec(void)

- ea: `0x18000bbe0`
- end: `0x18000bbf0`
- name: `??1CCritSec@@QEAA@XZ`
- size: `16`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800161a1`
- `0x1800161ba`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000bbe4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000bbe4`

## pseudocode

```c
void __fastcall CCritSec::~CCritSec(struct _RTL_CRITICAL_SECTION *this)
{
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x18000bbe0  sub     rsp, 28h
0x18000bbe4  call    cs:__imp_DeleteCriticalSection
0x18000bbea  nop
0x18000bbeb  add     rsp, 28h
0x18000bbef  retn
```
