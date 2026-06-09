# CleanupdbgPrintLock::~CleanupdbgPrintLock(void)

- ea: `0x180016840`
- end: `0x180016883`
- name: `??1CleanupdbgPrintLock@@QEAA@XZ`
- size: `67`
- prototype: `void __fastcall(CleanupdbgPrintLock *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18008d500`

## callees

- `0x180016840`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016854`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016854`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016866`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016866`

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
0x180016840  push    rbx
0x180016842  sub     rsp, 20h
0x180016846  mov     rbx, rcx
0x180016849  mov     rcx, [rcx]
0x18001684c  test    rcx, rcx
0x18001684f  jz      short loc_18001687C
0x180016851  mov     rcx, [rcx]; lpCriticalSection
0x180016854  call    cs:__imp_DeleteCriticalSection
0x18001685b  nop     dword ptr [rax+rax+00h]
0x180016860  mov     rcx, [rbx]
0x180016863  mov     rcx, [rcx]; hMem
0x180016866  call    cs:__imp_LocalFree
0x18001686d  nop     dword ptr [rax+rax+00h]
0x180016872  mov     rax, [rbx]
0x180016875  mov     qword ptr [rax], 0
0x18001687c  add     rsp, 20h
0x180016880  pop     rbx
0x180016881  retn
```
