# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180008b54`
- end: `0x180008b92`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `62`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ce20`

## callees

- `0x180002634`
- `0x180008b54`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180008b61`
- `KERNEL32!DeleteCriticalSection` at `0x180008b61`

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
0x180008b54  push    rbx
0x180008b56  sub     rsp, 20h
0x180008b5a  mov     rbx, rcx
0x180008b5d  add     rcx, 28h ; '('; lpCriticalSection
0x180008b61  call    cs:__imp_DeleteCriticalSection
0x180008b68  nop     dword ptr [rax+rax+00h]
0x180008b6d  mov     rcx, [rbx+50h]; Block
0x180008b71  test    rcx, rcx
0x180008b74  jz      short loc_180008B83
0x180008b76  call    free
0x180008b7b  mov     qword ptr [rbx+50h], 0
0x180008b83  mov     qword ptr [rbx+58h], 0
0x180008b8b  add     rsp, 20h
0x180008b8f  pop     rbx
0x180008b90  retn
```
