# CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::~CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>(void)

- ea: `0x180003350`
- end: `0x180003433`
- name: `??1?$CDlpActionImpl@V?$CDlpErrorImpl@V?$CDlpObjectInternalImpl@V?$CUnknownImpl@VIDlpAction@@@@@@@@@@UEAA@XZ`
- size: `227`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x1800036f0`
- `0x180003814`
- `0x180003db0`
- `0x180003f70`
- `0x1800045e0`

## callees

- `0x180003350`
- `0x180003478`
- `0x18001fd60`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003369`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003369`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003378`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003378`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800033a0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800033bd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800033da`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800033f7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003414`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800033a0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800033bd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800033da`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800033f7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003414`

## pseudocode

```c
__int64 __fastcall CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>::~CDlpActionImpl<CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>>(
        __int64 a1)
{
  __int64 v1; // rbx
  HANDLE ProcessHeap; // rax

  v1 = *(_QWORD *)(a1 + 496);
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v1 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    *(_QWORD *)(a1 + 496) = 0;
  }
  if ( *(_DWORD *)(a1 + 488) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 448));
    *(_DWORD *)(a1 + 488) = 0;
  }
  if ( *(_DWORD *)(a1 + 424) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 384));
    *(_DWORD *)(a1 + 424) = 0;
  }
  if ( *(_DWORD *)(a1 + 360) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 320));
    *(_DWORD *)(a1 + 360) = 0;
  }
  if ( *(_DWORD *)(a1 + 304) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 264));
    *(_DWORD *)(a1 + 304) = 0;
  }
  if ( *(_DWORD *)(a1 + 248) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 208));
    *(_DWORD *)(a1 + 248) = 0;
  }
  return CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>::~CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>(a1);
}

```

## disassembly

```asm
0x180003350  mov     [rsp+arg_0], rbx
0x180003355  push    rdi
0x180003356  sub     rsp, 20h
0x18000335a  mov     rbx, [rcx+1F0h]
0x180003361  mov     rdi, rcx
0x180003364  test    rbx, rbx
0x180003367  jz      short loc_180003390
0x180003369  call    cs:__imp_GetProcessHeap
0x18000336f  lea     r8, [rbx-4]; lpMem
0x180003373  xor     edx, edx; dwFlags
0x180003375  mov     rcx, rax; hHeap
0x180003378  call    cs:__imp_HeapFree
0x18000337e  xor     ecx, ecx
0x180003380  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180003385  mov     qword ptr [rdi+1F0h], 0
0x180003390  lea     rbx, [rdi+1C0h]
0x180003397  cmp     dword ptr [rbx+28h], 0
0x18000339b  jz      short loc_1800033AD
0x18000339d  mov     rcx, rbx; lpCriticalSection
0x1800033a0  call    cs:__imp_DeleteCriticalSection
0x1800033a6  mov     dword ptr [rbx+28h], 0
0x1800033ad  lea     rbx, [rdi+180h]
0x1800033b4  cmp     dword ptr [rbx+28h], 0
0x1800033b8  jz      short loc_1800033CA
0x1800033ba  mov     rcx, rbx; lpCriticalSection
0x1800033bd  call    cs:__imp_DeleteCriticalSection
0x1800033c3  mov     dword ptr [rbx+28h], 0
0x1800033ca  lea     rbx, [rdi+140h]
0x1800033d1  cmp     dword ptr [rbx+28h], 0
0x1800033d5  jz      short loc_1800033E7
0x1800033d7  mov     rcx, rbx; lpCriticalSection
0x1800033da  call    cs:__imp_DeleteCriticalSection
0x1800033e0  mov     dword ptr [rbx+28h], 0
0x1800033e7  lea     rbx, [rdi+108h]
0x1800033ee  cmp     dword ptr [rbx+28h], 0
0x1800033f2  jz      short loc_180003404
0x1800033f4  mov     rcx, rbx; lpCriticalSection
0x1800033f7  call    cs:__imp_DeleteCriticalSection
0x1800033fd  mov     dword ptr [rbx+28h], 0
0x180003404  lea     rbx, [rdi+0D0h]
0x18000340b  cmp     dword ptr [rbx+28h], 0
0x18000340f  jz      short loc_180003421
0x180003411  mov     rcx, rbx; lpCriticalSection
0x180003414  call    cs:__imp_DeleteCriticalSection
0x18000341a  mov     dword ptr [rbx+28h], 0
0x180003421  mov     rcx, rdi
0x180003424  mov     rbx, [rsp+28h+arg_0]
0x180003429  add     rsp, 20h
0x18000342d  pop     rdi
0x18000342e  jmp     ??1?$CDlpErrorImpl@V?$CDlpObjectInternalImpl@V?$CUnknownImpl@VIDlpAction@@@@@@@@UEAA@XZ; CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>::~CDlpErrorImpl<CDlpObjectInternalImpl<CUnknownImpl<IDlpAction>>>(void)
```
