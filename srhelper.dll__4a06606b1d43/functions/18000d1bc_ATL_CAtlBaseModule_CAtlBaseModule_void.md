# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x18000d1bc`
- end: `0x18000d1f4`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180015c40`

## callees

- `0x18000d1bc`

## import_xrefs

- `msvcrt!free` at `0x18000d1d8`
- `msvcrt!free` at `0x18000d1d8`
- `KERNEL32!DeleteCriticalSection` at `0x18000d1c9`
- `KERNEL32!DeleteCriticalSection` at `0x18000d1c9`

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
0x18000d1bc  push    rbx
0x18000d1be  sub     rsp, 20h
0x18000d1c2  mov     rbx, rcx
0x18000d1c5  add     rcx, 28h ; '('; lpCriticalSection
0x18000d1c9  call    cs:__imp_DeleteCriticalSection
0x18000d1cf  mov     rcx, [rbx+50h]; Block
0x18000d1d3  test    rcx, rcx
0x18000d1d6  jz      short loc_18000D1E6
0x18000d1d8  call    cs:__imp_free
0x18000d1de  mov     qword ptr [rbx+50h], 0
0x18000d1e6  mov     qword ptr [rbx+58h], 0
0x18000d1ee  add     rsp, 20h
0x18000d1f2  pop     rbx
0x18000d1f3  retn
```
