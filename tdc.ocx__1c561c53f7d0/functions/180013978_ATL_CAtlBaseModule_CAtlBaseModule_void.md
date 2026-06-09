# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180013978`
- end: `0x1800139b0`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800146d0`

## callees

- `0x180013978`

## import_xrefs

- `msvcrt!free` at `0x180013994`
- `msvcrt!free` at `0x180013994`
- `KERNEL32!DeleteCriticalSection` at `0x180013985`
- `KERNEL32!DeleteCriticalSection` at `0x180013985`

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
0x180013978  push    rbx
0x18001397a  sub     rsp, 20h
0x18001397e  mov     rbx, rcx
0x180013981  add     rcx, 28h ; '('; lpCriticalSection
0x180013985  call    cs:__imp_DeleteCriticalSection
0x18001398b  mov     rcx, [rbx+50h]; Block
0x18001398f  test    rcx, rcx
0x180013992  jz      short loc_1800139A2
0x180013994  call    cs:__imp_free
0x18001399a  mov     qword ptr [rbx+50h], 0
0x1800139a2  mov     qword ptr [rbx+58h], 0
0x1800139aa  add     rsp, 20h
0x1800139ae  pop     rbx
0x1800139af  retn
```
