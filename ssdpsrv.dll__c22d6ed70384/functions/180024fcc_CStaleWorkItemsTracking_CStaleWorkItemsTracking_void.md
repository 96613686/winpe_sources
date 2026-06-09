# CStaleWorkItemsTracking::~CStaleWorkItemsTracking(void)

- ea: `0x180024fcc`
- end: `0x180024ffa`
- name: `??1CStaleWorkItemsTracking@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180035530`
- `0x1800356b0`

## callees

- `0x18001cc6c`
- `0x180024fcc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180024ff3`

## pseudocode

```c
void __fastcall CStaleWorkItemsTracking::~CStaleWorkItemsTracking(struct _RTL_CRITICAL_SECTION *this)
{
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx

  DebugInfo = this[1].DebugInfo;
  if ( DebugInfo )
    CUList<CWorkItem *>::Node::`scalar deleting destructor'(DebugInfo);
  this[1].DebugInfo = 0;
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x180024fcc  push    rbx
0x180024fce  sub     rsp, 20h
0x180024fd2  mov     rbx, rcx
0x180024fd5  mov     rcx, [rcx+28h]; void *
0x180024fd9  test    rcx, rcx
0x180024fdc  jz      short loc_180024FE3
0x180024fde  call    ??_GNode@?$CUList@PEAVCWorkItem@@@@QEAAPEAXI@Z; CUList<CWorkItem *>::Node::`scalar deleting destructor'(uint)
0x180024fe3  mov     rcx, rbx
0x180024fe6  mov     qword ptr [rbx+28h], 0
0x180024fee  add     rsp, 20h
0x180024ff2  pop     rbx
0x180024ff3  jmp     cs:__imp_DeleteCriticalSection
```
