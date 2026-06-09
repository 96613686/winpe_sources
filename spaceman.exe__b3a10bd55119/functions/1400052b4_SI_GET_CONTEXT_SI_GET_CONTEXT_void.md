# SI_GET_CONTEXT::~SI_GET_CONTEXT(void)

- ea: `0x1400052b4`
- end: `0x1400052ea`
- name: `??1SI_GET_CONTEXT@@QEAA@XZ`
- size: `54`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140008e00`

## callees

- `0x1400052b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400052e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400052c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400052c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400052d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400052d5`

## pseudocode

```c
void __fastcall SI_GET_CONTEXT::~SI_GET_CONTEXT(struct _RTL_CRITICAL_SECTION *this)
{
  void *v2; // rcx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx

  v2 = *(void **)&this[1].LockCount;
  if ( v2 )
    LocalFree(v2);
  DebugInfo = this[1].DebugInfo;
  if ( DebugInfo )
    CloseHandle(DebugInfo);
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x1400052b4  push    rbx
0x1400052b6  sub     rsp, 20h
0x1400052ba  mov     rbx, rcx
0x1400052bd  mov     rcx, [rcx+30h]; hMem
0x1400052c1  test    rcx, rcx
0x1400052c4  jz      short loc_1400052CC
0x1400052c6  call    cs:__imp_LocalFree
0x1400052cc  mov     rcx, [rbx+28h]; hObject
0x1400052d0  test    rcx, rcx
0x1400052d3  jz      short loc_1400052DB
0x1400052d5  call    cs:__imp_CloseHandle
0x1400052db  mov     rcx, rbx
0x1400052de  add     rsp, 20h
0x1400052e2  pop     rbx
0x1400052e3  jmp     cs:__imp_DeleteCriticalSection
```
