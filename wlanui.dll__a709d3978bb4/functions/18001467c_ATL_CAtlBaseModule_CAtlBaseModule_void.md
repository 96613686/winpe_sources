# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x18001467c`
- end: `0x1800146b4`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(ATL::CAtlBaseModule *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001c540`

## callees

- `0x18001467c`

## import_xrefs

- `msvcrt!free` at `0x180014698`
- `msvcrt!free` at `0x180014698`
- `KERNEL32!DeleteCriticalSection` at `0x180014689`
- `KERNEL32!DeleteCriticalSection` at `0x180014689`

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
0x18001467c  push    rbx
0x18001467e  sub     rsp, 20h
0x180014682  mov     rbx, rcx
0x180014685  add     rcx, 28h ; '('; lpCriticalSection
0x180014689  call    cs:__imp_DeleteCriticalSection
0x18001468f  mov     rcx, [rbx+50h]; Block
0x180014693  test    rcx, rcx
0x180014696  jz      short loc_1800146A6
0x180014698  call    cs:__imp_free
0x18001469e  mov     qword ptr [rbx+50h], 0
0x1800146a6  mov     qword ptr [rbx+58h], 0
0x1800146ae  add     rsp, 20h
0x1800146b2  pop     rbx
0x1800146b3  retn
```
