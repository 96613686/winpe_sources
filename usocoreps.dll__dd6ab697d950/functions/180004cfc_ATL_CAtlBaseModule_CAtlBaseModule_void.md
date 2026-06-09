# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180004cfc`
- end: `0x180004d33`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005130`

## callees

- `0x1800020ee`
- `0x180004cfc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004d09`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004d09`

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
0x180004cfc  push    rbx
0x180004cfe  sub     rsp, 20h
0x180004d02  mov     rbx, rcx
0x180004d05  add     rcx, 28h ; '('; lpCriticalSection
0x180004d09  call    cs:__imp_DeleteCriticalSection
0x180004d0f  mov     rcx, [rbx+50h]; Block
0x180004d13  test    rcx, rcx
0x180004d16  jz      short loc_180004D25
0x180004d18  call    free
0x180004d1d  mov     qword ptr [rbx+50h], 0
0x180004d25  mov     qword ptr [rbx+58h], 0
0x180004d2d  add     rsp, 20h
0x180004d31  pop     rbx
0x180004d32  retn
```
