# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x18002fd6c`
- end: `0x18002fda3`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180039930`

## callees

- `0x18002fd6c`
- `0x18002ff2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002fd79`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002fd79`

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
0x18002fd6c  push    rbx
0x18002fd6e  sub     rsp, 20h
0x18002fd72  mov     rbx, rcx
0x18002fd75  add     rcx, 28h ; '('; lpCriticalSection
0x18002fd79  call    cs:__imp_DeleteCriticalSection
0x18002fd7f  mov     rcx, [rbx+50h]; Block
0x18002fd83  test    rcx, rcx
0x18002fd86  jz      short loc_18002FD95
0x18002fd88  call    free
0x18002fd8d  mov     qword ptr [rbx+50h], 0
0x18002fd95  mov     qword ptr [rbx+58h], 0
0x18002fd9d  add     rsp, 20h
0x18002fda1  pop     rbx
0x18002fda2  retn
```
