# ATL::CAtlBaseModule::~CAtlBaseModule(void)

- ea: `0x1800156e0`
- end: `0x180015718`
- name: `??1CAtlBaseModule@ATL@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180021d60`

## callees

- `0x1800156e0`

## import_xrefs

- `msvcrt!free` at `0x1800156fc`
- `msvcrt!free` at `0x1800156fc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800156ed`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800156ed`

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
0x1800156e0  push    rbx
0x1800156e2  sub     rsp, 20h
0x1800156e6  mov     rbx, rcx
0x1800156e9  add     rcx, 28h ; '('; lpCriticalSection
0x1800156ed  call    cs:__imp_DeleteCriticalSection
0x1800156f3  mov     rcx, [rbx+50h]; Block
0x1800156f7  test    rcx, rcx
0x1800156fa  jz      short loc_18001570A
0x1800156fc  call    cs:__imp_free
0x180015702  mov     qword ptr [rbx+50h], 0
0x18001570a  mov     qword ptr [rbx+58h], 0
0x180015712  add     rsp, 20h
0x180015716  pop     rbx
0x180015717  retn
```
