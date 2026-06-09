# CStaticCritSec::~CStaticCritSec(void)

- ea: `0x180028bb0`
- end: `0x180028bc6`
- name: `??1CStaticCritSec@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180034060`
- `0x18004597d`

## callees

- `0x180028bb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180028bba`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180028bba`

## pseudocode

```c
void __fastcall CStaticCritSec::~CStaticCritSec(struct _RTL_CRITICAL_SECTION *this)
{
  if ( LOBYTE(this[1].DebugInfo) )
    DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x180028bb0  sub     rsp, 28h
0x180028bb4  cmp     byte ptr [rcx+28h], 0
0x180028bb8  jz      short loc_180028BC1
0x180028bba  call    cs:__imp_DeleteCriticalSection
0x180028bc0  nop
0x180028bc1  add     rsp, 28h
0x180028bc5  retn
```
