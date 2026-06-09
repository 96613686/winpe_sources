# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180048db4`
- end: `0x180048deb`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18004ba30`

## callees

- `0x1800425cc`
- `0x180048db4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180048dc1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180048dc1`

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
0x180048db4  push    rbx
0x180048db6  sub     rsp, 20h
0x180048dba  mov     rbx, rcx
0x180048dbd  add     rcx, 28h ; '('; lpCriticalSection
0x180048dc1  call    cs:__imp_DeleteCriticalSection
0x180048dc7  mov     rcx, [rbx+50h]; Block
0x180048dcb  test    rcx, rcx
0x180048dce  jz      short loc_180048DDD
0x180048dd0  call    free
0x180048dd5  mov     qword ptr [rbx+50h], 0
0x180048ddd  mov     qword ptr [rbx+58h], 0
0x180048de5  add     rsp, 20h
0x180048de9  pop     rbx
0x180048dea  retn
```
