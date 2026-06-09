# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180068800`
- end: `0x180068838`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18006e4e0`

## callees

- `0x180068800`

## import_xrefs

- `msvcrt!free` at `0x18006881c`
- `msvcrt!free` at `0x18006881c`
- `KERNEL32!DeleteCriticalSection` at `0x18006880d`
- `KERNEL32!DeleteCriticalSection` at `0x18006880d`

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
0x180068800  push    rbx
0x180068802  sub     rsp, 20h
0x180068806  mov     rbx, rcx
0x180068809  add     rcx, 28h ; '('; lpCriticalSection
0x18006880d  call    cs:__imp_DeleteCriticalSection
0x180068813  mov     rcx, [rbx+50h]; Block
0x180068817  test    rcx, rcx
0x18006881a  jz      short loc_18006882A
0x18006881c  call    cs:__imp_free
0x180068822  mov     qword ptr [rbx+50h], 0
0x18006882a  mov     qword ptr [rbx+58h], 0
0x180068832  add     rsp, 20h
0x180068836  pop     rbx
0x180068837  retn
```
