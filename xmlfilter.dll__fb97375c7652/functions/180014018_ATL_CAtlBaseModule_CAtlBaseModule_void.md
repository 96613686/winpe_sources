# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180014018`
- end: `0x18001404f`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800161b0`

## callees

- `0x180002b14`
- `0x180014018`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014025`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014025`

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
0x180014018  push    rbx
0x18001401a  sub     rsp, 20h
0x18001401e  mov     rbx, rcx
0x180014021  add     rcx, 28h ; '('; lpCriticalSection
0x180014025  call    cs:__imp_DeleteCriticalSection
0x18001402b  mov     rcx, [rbx+50h]; Block
0x18001402f  test    rcx, rcx
0x180014032  jz      short loc_180014041
0x180014034  call    free
0x180014039  mov     qword ptr [rbx+50h], 0
0x180014041  mov     qword ptr [rbx+58h], 0
0x180014049  add     rsp, 20h
0x18001404d  pop     rbx
0x18001404e  retn
```
