# CSsdpServiceManager::~CSsdpServiceManager(void)

- ea: `0x180024f98`
- end: `0x180024fc6`
- name: `??1CSsdpServiceManager@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180035630`

## callees

- `0x180024f98`
- `0x18002faf8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180024fbf`

## pseudocode

```c
void __fastcall CSsdpServiceManager::~CSsdpServiceManager(struct _RTL_CRITICAL_SECTION *this)
{
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx

  DebugInfo = this[1].DebugInfo;
  if ( DebugInfo )
    CUList<CSsdpService>::Node::`scalar deleting destructor'(DebugInfo);
  this[1].DebugInfo = 0;
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x180024f98  push    rbx
0x180024f9a  sub     rsp, 20h
0x180024f9e  mov     rbx, rcx
0x180024fa1  mov     rcx, [rcx+28h]; void *
0x180024fa5  test    rcx, rcx
0x180024fa8  jz      short loc_180024FAF
0x180024faa  call    ??_GNode@?$CUList@VCSsdpService@@@@QEAAPEAXI@Z; CUList<CSsdpService>::Node::`scalar deleting destructor'(uint)
0x180024faf  mov     rcx, rbx
0x180024fb2  mov     qword ptr [rbx+28h], 0
0x180024fba  add     rsp, 20h
0x180024fbe  pop     rbx
0x180024fbf  jmp     cs:__imp_DeleteCriticalSection
```
