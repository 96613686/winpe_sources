# CSsdpServiceManager::~CSsdpServiceManager(void)

- ea: `0x180026d58`
- end: `0x180026d8b`
- name: `??1CSsdpServiceManager@@QEAA@XZ`
- size: `51`
- prototype: `void __fastcall(CSsdpServiceManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180038180`

## callees

- `0x180026d58`
- `0x180031df8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180026d7f`

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
0x180026d58  push    rbx
0x180026d5a  sub     rsp, 20h
0x180026d5e  mov     rbx, rcx
0x180026d61  mov     rcx, [rcx+28h]; void *
0x180026d65  test    rcx, rcx
0x180026d68  jz      short loc_180026D6F
0x180026d6a  call    ??_GNode@?$CUList@VCSsdpService@@@@QEAAPEAXI@Z; CUList<CSsdpService>::Node::`scalar deleting destructor'(uint)
0x180026d6f  mov     rcx, rbx
0x180026d72  mov     qword ptr [rbx+28h], 0
0x180026d7a  add     rsp, 20h
0x180026d7e  pop     rbx
0x180026d7f  jmp     cs:__imp_DeleteCriticalSection
```
