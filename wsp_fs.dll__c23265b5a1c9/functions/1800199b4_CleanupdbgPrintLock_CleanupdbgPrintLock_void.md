# CleanupdbgPrintLock::~CleanupdbgPrintLock(void)

- ea: `0x1800199b4`
- end: `0x1800199f7`
- name: `??1CleanupdbgPrintLock@@QEAA@XZ`
- size: `67`
- prototype: `void __fastcall(CleanupdbgPrintLock *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800aa130`

## callees

- `0x1800199b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800199c8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800199c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800199da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800199da`

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
0x1800199b4  push    rbx
0x1800199b6  sub     rsp, 20h
0x1800199ba  mov     rbx, rcx
0x1800199bd  mov     rcx, [rcx]
0x1800199c0  test    rcx, rcx
0x1800199c3  jz      short loc_1800199F0
0x1800199c5  mov     rcx, [rcx]; lpCriticalSection
0x1800199c8  call    cs:__imp_DeleteCriticalSection
0x1800199cf  nop     dword ptr [rax+rax+00h]
0x1800199d4  mov     rcx, [rbx]
0x1800199d7  mov     rcx, [rcx]; hMem
0x1800199da  call    cs:__imp_LocalFree
0x1800199e1  nop     dword ptr [rax+rax+00h]
0x1800199e6  mov     rax, [rbx]
0x1800199e9  mov     qword ptr [rax], 0
0x1800199f0  add     rsp, 20h
0x1800199f4  pop     rbx
0x1800199f5  retn
```
