# CSsdpCacheEntryManager::~CSsdpCacheEntryManager(void)

- ea: `0x180026ce0`
- end: `0x180026d13`
- name: `??1CSsdpCacheEntryManager@@QEAA@XZ`
- size: `51`
- prototype: `void __fastcall(CSsdpCacheEntryManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180038100`

## callees

- `0x18000bad0`
- `0x180026ce0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180026d07`

## pseudocode

```c
void __fastcall CSsdpCacheEntryManager::~CSsdpCacheEntryManager(struct _RTL_CRITICAL_SECTION *this)
{
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx

  DebugInfo = this[1].DebugInfo;
  if ( DebugInfo )
    CUList<CSsdpCacheEntry>::Node::`scalar deleting destructor'(DebugInfo);
  this[1].DebugInfo = 0;
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x180026ce0  push    rbx
0x180026ce2  sub     rsp, 20h
0x180026ce6  mov     rbx, rcx
0x180026ce9  mov     rcx, [rcx+28h]; void *
0x180026ced  test    rcx, rcx
0x180026cf0  jz      short loc_180026CF7
0x180026cf2  call    ??_GNode@?$CUList@VCSsdpCacheEntry@@@@QEAAPEAXI@Z; CUList<CSsdpCacheEntry>::Node::`scalar deleting destructor'(uint)
0x180026cf7  mov     rcx, rbx
0x180026cfa  mov     qword ptr [rbx+28h], 0
0x180026d02  add     rsp, 20h
0x180026d06  pop     rbx
0x180026d07  jmp     cs:__imp_DeleteCriticalSection
```
