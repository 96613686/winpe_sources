# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x1800193fc`
- end: `0x180019434`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001a7c0`

## callees

- `0x1800193fc`

## import_xrefs

- `msvcrt!free` at `0x180019418`
- `msvcrt!free` at `0x180019418`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180019409`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180019409`

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
0x1800193fc  push    rbx
0x1800193fe  sub     rsp, 20h
0x180019402  mov     rbx, rcx
0x180019405  add     rcx, 28h ; '('; lpCriticalSection
0x180019409  call    cs:__imp_DeleteCriticalSection
0x18001940f  mov     rcx, [rbx+50h]; Block
0x180019413  test    rcx, rcx
0x180019416  jz      short loc_180019426
0x180019418  call    cs:__imp_free
0x18001941e  mov     qword ptr [rbx+50h], 0
0x180019426  mov     qword ptr [rbx+58h], 0
0x18001942e  add     rsp, 20h
0x180019432  pop     rbx
0x180019433  retn
```
