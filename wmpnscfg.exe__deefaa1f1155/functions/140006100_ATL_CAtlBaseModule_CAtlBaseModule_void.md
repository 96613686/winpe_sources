# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x140006100`
- end: `0x140006137`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140007810`

## callees

- `0x140001e76`
- `0x140006100`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14000610d`
- `KERNEL32!DeleteCriticalSection` at `0x14000610d`

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
0x140006100  push    rbx
0x140006102  sub     rsp, 20h
0x140006106  mov     rbx, rcx
0x140006109  add     rcx, 28h ; '('; lpCriticalSection
0x14000610d  call    cs:__imp_DeleteCriticalSection
0x140006113  mov     rcx, [rbx+50h]; Block
0x140006117  test    rcx, rcx
0x14000611a  jz      short loc_140006129
0x14000611c  call    free
0x140006121  mov     qword ptr [rbx+50h], 0
0x140006129  mov     qword ptr [rbx+58h], 0
0x140006131  add     rsp, 20h
0x140006135  pop     rbx
0x140006136  retn
```
