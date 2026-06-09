# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180031018`
- end: `0x18003105d`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `69`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180033ed0`

## callees

- `0x180031018`

## import_xrefs

- `msvcrt!free` at `0x18003103a`
- `msvcrt!free` at `0x18003103a`
- `KERNEL32!DeleteCriticalSection` at `0x180031025`
- `KERNEL32!DeleteCriticalSection` at `0x180031025`

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
0x180031018  push    rbx
0x18003101a  sub     rsp, 20h
0x18003101e  mov     rbx, rcx
0x180031021  add     rcx, 28h ; '('; lpCriticalSection
0x180031025  call    cs:__imp_DeleteCriticalSection
0x18003102c  nop     dword ptr [rax+rax+00h]
0x180031031  mov     rcx, [rbx+50h]; Block
0x180031035  test    rcx, rcx
0x180031038  jz      short loc_18003104E
0x18003103a  call    cs:__imp_free
0x180031041  nop     dword ptr [rax+rax+00h]
0x180031046  mov     qword ptr [rbx+50h], 0
0x18003104e  mov     qword ptr [rbx+58h], 0
0x180031056  add     rsp, 20h
0x18003105a  pop     rbx
0x18003105b  retn
```
