# CleanupdbgPrintLock::~CleanupdbgPrintLock(void)

- ea: `0x180019078`
- end: `0x1800190ae`
- name: `??1CleanupdbgPrintLock@@QEAA@XZ`
- size: `54`
- prototype: `void __fastcall(CleanupdbgPrintLock *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800a7e60`

## callees

- `0x180019078`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001908c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001908c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019098`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019098`

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
0x180019078  push    rbx
0x18001907a  sub     rsp, 20h
0x18001907e  mov     rbx, rcx
0x180019081  mov     rcx, [rcx]
0x180019084  test    rcx, rcx
0x180019087  jz      short loc_1800190A8
0x180019089  mov     rcx, [rcx]; lpCriticalSection
0x18001908c  call    cs:__imp_DeleteCriticalSection
0x180019092  mov     rcx, [rbx]
0x180019095  mov     rcx, [rcx]; hMem
0x180019098  call    cs:__imp_LocalFree
0x18001909e  mov     rax, [rbx]
0x1800190a1  mov     qword ptr [rax], 0
0x1800190a8  add     rsp, 20h
0x1800190ac  pop     rbx
0x1800190ad  retn
```
