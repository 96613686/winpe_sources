# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x18001aeb0`
- end: `0x18001aee8`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001b650`

## callees

- `0x18001aeb0`

## import_xrefs

- `msvcrt!free` at `0x18001aecc`
- `msvcrt!free` at `0x18001aecc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001aebd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001aebd`

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
0x18001aeb0  push    rbx
0x18001aeb2  sub     rsp, 20h
0x18001aeb6  mov     rbx, rcx
0x18001aeb9  add     rcx, 28h ; '('; lpCriticalSection
0x18001aebd  call    cs:__imp_DeleteCriticalSection
0x18001aec3  mov     rcx, [rbx+50h]; Block
0x18001aec7  test    rcx, rcx
0x18001aeca  jz      short loc_18001AEDA
0x18001aecc  call    cs:__imp_free
0x18001aed2  mov     qword ptr [rbx+50h], 0
0x18001aeda  mov     qword ptr [rbx+58h], 0
0x18001aee2  add     rsp, 20h
0x18001aee6  pop     rbx
0x18001aee7  retn
```
