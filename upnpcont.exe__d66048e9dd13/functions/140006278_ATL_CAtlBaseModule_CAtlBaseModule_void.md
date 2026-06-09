# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x140006278`
- end: `0x1400062af`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400067c0`

## callees

- `0x140001df4`
- `0x140006278`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140006285`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140006285`

## pseudocode

```c
void __fastcall ATL::CAtlBaseModule::~CAtlBaseModule(struct _RTL_CRITICAL_SECTION *this)
{
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx

  DeleteCriticalSection(this + 1);
  DebugInfo = this[2].DebugInfo;
  if ( DebugInfo )
  {
    free(DebugInfo);
    this[2].DebugInfo = 0;
  }
  *(_QWORD *)&this[2].LockCount = 0;
}

```

## disassembly

```asm
0x140006278  push    rbx
0x14000627a  sub     rsp, 20h
0x14000627e  mov     rbx, rcx
0x140006281  add     rcx, 28h ; '('; lpCriticalSection
0x140006285  call    cs:__imp_DeleteCriticalSection
0x14000628b  mov     rcx, [rbx+50h]; Block
0x14000628f  test    rcx, rcx
0x140006292  jz      short loc_1400062A1
0x140006294  call    free
0x140006299  mov     qword ptr [rbx+50h], 0
0x1400062a1  mov     qword ptr [rbx+58h], 0
0x1400062a9  add     rsp, 20h
0x1400062ad  pop     rbx
0x1400062ae  retn
```
