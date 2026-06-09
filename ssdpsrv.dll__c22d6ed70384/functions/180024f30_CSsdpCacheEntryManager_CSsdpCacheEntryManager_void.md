# CSsdpCacheEntryManager::~CSsdpCacheEntryManager(void)

- ea: `0x180024f30`
- end: `0x180024f5e`
- name: `??1CSsdpCacheEntryManager@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800355b0`

## callees

- `0x18000a3f0`
- `0x180024f30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180024f57`

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
0x180024f30  push    rbx
0x180024f32  sub     rsp, 20h
0x180024f36  mov     rbx, rcx
0x180024f39  mov     rcx, [rcx+28h]; void *
0x180024f3d  test    rcx, rcx
0x180024f40  jz      short loc_180024F47
0x180024f42  call    ??_GNode@?$CUList@VCSsdpCacheEntry@@@@QEAAPEAXI@Z; CUList<CSsdpCacheEntry>::Node::`scalar deleting destructor'(uint)
0x180024f47  mov     rcx, rbx
0x180024f4a  mov     qword ptr [rbx+28h], 0
0x180024f52  add     rsp, 20h
0x180024f56  pop     rbx
0x180024f57  jmp     cs:__imp_DeleteCriticalSection
```
