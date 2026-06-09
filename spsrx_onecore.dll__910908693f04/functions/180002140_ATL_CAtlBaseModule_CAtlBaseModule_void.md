# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x180002140`
- end: `0x180002177`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `55`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003660`

## callees

- `0x180002140`
- `0x180002eb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000214d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000214d`

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
0x180002140  push    rbx
0x180002142  sub     rsp, 20h
0x180002146  mov     rbx, rcx
0x180002149  add     rcx, 28h ; '('; lpCriticalSection
0x18000214d  call    cs:__imp_DeleteCriticalSection
0x180002153  mov     rcx, [rbx+50h]; Block
0x180002157  test    rcx, rcx
0x18000215a  jz      short loc_180002169
0x18000215c  call    free
0x180002161  mov     qword ptr [rbx+50h], 0
0x180002169  mov     qword ptr [rbx+58h], 0
0x180002171  add     rsp, 20h
0x180002175  pop     rbx
0x180002176  retn
```
