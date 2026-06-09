# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x1800119b0`
- end: `0x1800119f5`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `69`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800132c0`

## callees

- `0x1800119b0`

## import_xrefs

- `msvcrt!free` at `0x1800119d2`
- `msvcrt!free` at `0x1800119d2`
- `KERNEL32!DeleteCriticalSection` at `0x1800119bd`
- `KERNEL32!DeleteCriticalSection` at `0x1800119bd`

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
0x1800119b0  push    rbx
0x1800119b2  sub     rsp, 20h
0x1800119b6  mov     rbx, rcx
0x1800119b9  add     rcx, 28h ; '('; lpCriticalSection
0x1800119bd  call    cs:__imp_DeleteCriticalSection
0x1800119c4  nop     dword ptr [rax+rax+00h]
0x1800119c9  mov     rcx, [rbx+50h]; Block
0x1800119cd  test    rcx, rcx
0x1800119d0  jz      short loc_1800119E6
0x1800119d2  call    cs:__imp_free
0x1800119d9  nop     dword ptr [rax+rax+00h]
0x1800119de  mov     qword ptr [rbx+50h], 0
0x1800119e6  mov     qword ptr [rbx+58h], 0
0x1800119ee  add     rsp, 20h
0x1800119f2  pop     rbx
0x1800119f3  retn
```
