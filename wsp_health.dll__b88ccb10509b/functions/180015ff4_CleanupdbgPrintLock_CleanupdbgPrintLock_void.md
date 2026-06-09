# CleanupdbgPrintLock::~CleanupdbgPrintLock(void)

- ea: `0x180015ff4`
- end: `0x18001602a`
- name: `??1CleanupdbgPrintLock@@QEAA@XZ`
- size: `54`
- prototype: `void __fastcall(CleanupdbgPrintLock *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18008af60`

## callees

- `0x180015ff4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016008`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016008`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016014`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016014`

## pseudocode

```c
void __fastcall CleanupdbgPrintLock::~CleanupdbgPrintLock(HLOCAL **this)
{
  HLOCAL *v2; // rcx

  v2 = *this;
  if ( v2 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)*v2);
    LocalFree(**this);
    **this = 0;
  }
}

```

## disassembly

```asm
0x180015ff4  push    rbx
0x180015ff6  sub     rsp, 20h
0x180015ffa  mov     rbx, rcx
0x180015ffd  mov     rcx, [rcx]
0x180016000  test    rcx, rcx
0x180016003  jz      short loc_180016024
0x180016005  mov     rcx, [rcx]; lpCriticalSection
0x180016008  call    cs:__imp_DeleteCriticalSection
0x18001600e  mov     rcx, [rbx]
0x180016011  mov     rcx, [rcx]; hMem
0x180016014  call    cs:__imp_LocalFree
0x18001601a  mov     rax, [rbx]
0x18001601d  mov     qword ptr [rax], 0
0x180016024  add     rsp, 20h
0x180016028  pop     rbx
0x180016029  retn
```
