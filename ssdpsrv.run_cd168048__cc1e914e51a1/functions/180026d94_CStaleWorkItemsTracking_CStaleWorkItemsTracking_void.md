# CStaleWorkItemsTracking::~CStaleWorkItemsTracking(void)

- ea: `0x180026d94`
- end: `0x180026dc7`
- name: `??1CStaleWorkItemsTracking@@QEAA@XZ`
- size: `51`
- prototype: `void __fastcall(CStaleWorkItemsTracking *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180038060`
- `0x180038200`

## callees

- `0x18001e110`
- `0x180026d94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180026dbb`

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
0x180026d94  push    rbx
0x180026d96  sub     rsp, 20h
0x180026d9a  mov     rbx, rcx
0x180026d9d  mov     rcx, [rcx+28h]; void *
0x180026da1  test    rcx, rcx
0x180026da4  jz      short loc_180026DAB
0x180026da6  call    ??_GNode@?$CUList@PEAVCWorkItem@@@@QEAAPEAXI@Z; CUList<CWorkItem *>::Node::`scalar deleting destructor'(uint)
0x180026dab  mov     rcx, rbx
0x180026dae  mov     qword ptr [rbx+28h], 0
0x180026db6  add     rsp, 20h
0x180026dba  pop     rbx
0x180026dbb  jmp     cs:__imp_DeleteCriticalSection
```
