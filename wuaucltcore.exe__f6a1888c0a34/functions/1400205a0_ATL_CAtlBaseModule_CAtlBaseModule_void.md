# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x1400205a0`
- end: `0x1400205d7`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140022160`

## callees

- `0x14001aa0c`
- `0x1400205a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400205ad`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400205ad`

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
0x1400205a0  push    rbx
0x1400205a2  sub     rsp, 20h
0x1400205a6  mov     rbx, rcx
0x1400205a9  add     rcx, 28h ; '('; lpCriticalSection
0x1400205ad  call    cs:__imp_DeleteCriticalSection
0x1400205b3  mov     rcx, [rbx+50h]; Block
0x1400205b7  test    rcx, rcx
0x1400205ba  jz      short loc_1400205C9
0x1400205bc  call    free
0x1400205c1  mov     qword ptr [rbx+50h], 0
0x1400205c9  mov     qword ptr [rbx+58h], 0
0x1400205d1  add     rsp, 20h
0x1400205d5  pop     rbx
0x1400205d6  retn
```
