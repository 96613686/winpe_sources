# SP<CTokenActivation::CSmartCardDetector,SP_COM<CTokenActivation::CSmartCardDetector>>::~SP<CTokenActivation::CSmartCardDetector,SP_COM<CTokenActivation::CSmartCardDetector>>(void)

- ea: `0x180036fc4`
- end: `0x180037047`
- name: `??1?$SP@VCSmartCardDetector@CTokenActivation@@V?$SP_COM@VCSmartCardDetector@CTokenActivation@@@@@@QEAA@XZ`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18003a474`

## callees

- `0x18001a134`
- `0x180036fc4`
- `0x180037050`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037014`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037014`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037028`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037028`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036ff7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036ff7`

## pseudocode

```c
void __fastcall SP<CTokenActivation::CSmartCardDetector,SP_COM<CTokenActivation::CSmartCardDetector>>::~SP<CTokenActivation::CSmartCardDetector,SP_COM<CTokenActivation::CSmartCardDetector>>(
        __int64 *a1)
{
  __int64 v1; // rbx
  void *v3; // rcx
  HANDLE ProcessHeap; // rax

  v1 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v1, 0xFFFFFFFF) == 1 )
    {
      SP<CRefCountWrapper<DH_HANDLE>,SP_COM<CRefCountWrapper<DH_HANDLE>>>::~SP<CRefCountWrapper<DH_HANDLE>,SP_COM<CRefCountWrapper<DH_HANDLE>>>((_QWORD **)(v1 + 72));
      v3 = *(void **)(v1 + 32);
      if ( v3 )
      {
        CloseHandle(v3);
        *(_QWORD *)(v1 + 32) = 0;
      }
      SP<DH_HANDLE,SP_CPP_ARRAY<DH_HANDLE>>::~SP<DH_HANDLE,SP_CPP_ARRAY<DH_HANDLE>>(v1 + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, (LPVOID)v1);
    }
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x180036fc4  mov     [rsp+arg_0], rbx
0x180036fc9  push    rdi
0x180036fca  sub     rsp, 20h
0x180036fce  mov     rbx, [rcx]
0x180036fd1  mov     rdi, rcx
0x180036fd4  test    rbx, rbx
0x180036fd7  jz      short loc_18003703B
0x180036fd9  or      eax, 0FFFFFFFFh
0x180036fdc  lock xadd [rbx], eax
0x180036fe0  cmp     eax, 1
0x180036fe3  jnz     short loc_180037034
0x180036fe5  lea     rcx, [rbx+48h]
0x180036fe9  call    ??1?$SP@V?$CRefCountWrapper@VDH_HANDLE@@@@V?$SP_COM@V?$CRefCountWrapper@VDH_HANDLE@@@@@@@@QEAA@XZ; SP<CRefCountWrapper<DH_HANDLE>,SP_COM<CRefCountWrapper<DH_HANDLE>>>::~SP<CRefCountWrapper<DH_HANDLE>,SP_COM<CRefCountWrapper<DH_HANDLE>>>(void)
0x180036fee  mov     rcx, [rbx+20h]; hObject
0x180036ff2  test    rcx, rcx
0x180036ff5  jz      short loc_18003700B
0x180036ff7  call    cs:__imp_CloseHandle
0x180036ffe  nop     dword ptr [rax+rax+00h]
0x180037003  mov     qword ptr [rbx+20h], 0
0x18003700b  lea     rcx, [rbx+8]
0x18003700f  call    ??1?$SP@VDH_HANDLE@@V?$SP_CPP_ARRAY@VDH_HANDLE@@@@@@QEAA@XZ; SP<DH_HANDLE,SP_CPP_ARRAY<DH_HANDLE>>::~SP<DH_HANDLE,SP_CPP_ARRAY<DH_HANDLE>>(void)
0x180037014  call    cs:__imp_GetProcessHeap
0x18003701b  nop     dword ptr [rax+rax+00h]
0x180037020  mov     r8, rbx; lpMem
0x180037023  xor     edx, edx; dwFlags
0x180037025  mov     rcx, rax; hHeap
0x180037028  call    cs:__imp_HeapFree
0x18003702f  nop     dword ptr [rax+rax+00h]
0x180037034  mov     qword ptr [rdi], 0
0x18003703b  mov     rbx, [rsp+28h+arg_0]
0x180037040  add     rsp, 20h
0x180037044  pop     rdi
0x180037045  retn
```
