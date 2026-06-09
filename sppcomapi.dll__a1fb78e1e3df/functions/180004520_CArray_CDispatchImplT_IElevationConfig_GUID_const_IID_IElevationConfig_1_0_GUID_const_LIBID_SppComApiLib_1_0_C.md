# CArray<CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,ulong,CAdaptorDefault,CPoliciesDefault>::SetSize(int)

- ea: `0x180004520`
- end: `0x180004666`
- name: `?SetSize@?$CArray@UCTypeInfoItem@?$CDispatchImplT@UIElevationConfig@@$1?IID_IElevationConfig@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@KVCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z`
- size: `326`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `17`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000405c`
- `0x180004950`
- `0x180019b4c`
- `0x180019db0`
- `0x180019e48`
- `0x180019ee0`
- `0x180019f78`
- `0x18001a010`
- `0x18001b530`
- `0x18001b6cc`
- `0x18001b864`
- `0x18001ba44`
- `0x18001e0a8`
- `0x18001e3c8`
- `0x18001e460`
- `0x180020e90`
- `0x180038f90`

## callees

- `0x180003520`
- `0x180004288`
- `0x180004520`
- `0x18003c512`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004559`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800045f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004634`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004559`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800045f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004634`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004604`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004648`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004604`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004648`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000456d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000456d`

## pseudocode

```c
__int64 __fastcall CArray<CDispatchImplT<IElevationConfig,&_GUID const IID_IElevationConfig,1,0,&_GUID const LIBID_SppComApiLib,1,0>::CTypeInfoItem,unsigned long,CAdaptorDefault,CPoliciesDefault>::SetSize(
        __int64 a1,
        int a2)
{
  __int64 v2; // rsi
  void *v3; // rbx
  int v5; // ebp
  HANDLE v6; // rax
  void *v7; // rax
  unsigned int v8; // edi
  void *v9; // r15
  void *v10; // r12
  int v11; // ebx
  _QWORD *v12; // r14
  void *v13; // r14
  HANDLE ProcessHeap; // rax
  void *v15; // rax

  v2 = a2;
  v3 = 0;
  if ( *(_DWORD *)a1 == a2 )
  {
LABEL_20:
    v8 = 0;
    goto LABEL_21;
  }
  v5 = *(_DWORD *)(a1 + 4);
  if ( a2 < v5 )
    v5 = a2;
  if ( a2 <= 0 )
  {
LABEL_9:
    v9 = v3;
    v10 = v3;
    if ( (int)v2 < *(_DWORD *)(a1 + 4) )
    {
      v11 = v2;
      do
      {
        v12 = (_QWORD *)(*(_QWORD *)(a1 + 8) + 16LL * v11);
        if ( v12 && *v12 )
        {
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v12 + 16LL))(*v12);
          *v12 = 0;
        }
        ++v11;
      }
      while ( v11 < *(_DWORD *)(a1 + 4) );
    }
    v13 = *(void **)(a1 + 8);
    if ( v13 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v13);
      *(_QWORD *)(a1 + 8) = 0;
    }
    v15 = 0;
    if ( v9 )
      v15 = v10;
    *(_QWORD *)(a1 + 8) = v15;
    *(_DWORD *)(a1 + 4) = v5;
    *(_DWORD *)a1 = v2;
    goto LABEL_20;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  v6 = GetProcessHeap();
  v7 = HeapAlloc(v6, 0, 16 * v2);
  v3 = v7;
  if ( v7 )
  {
    if ( v5 )
      memcpy_0(v7, *(const void **)(a1 + 8), 16LL * v5);
    goto LABEL_9;
  }
  v8 = -2147024882;
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942414LL);
LABEL_21:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
  return v8;
}

```

## disassembly

```asm
0x180004520  push    rbx
0x180004522  push    rbp
0x180004523  push    rsi
0x180004524  push    rdi
0x180004525  push    r12
0x180004527  push    r14
0x180004529  push    r15
0x18000452b  sub     rsp, 20h
0x18000452f  movsxd  rsi, edx
0x180004532  xor     ebx, ebx
0x180004534  mov     rdi, rcx
0x180004537  cmp     [rcx], esi
0x180004539  jz      loc_180004626
0x18000453f  mov     ebp, [rcx+4]
0x180004542  cmp     esi, ebp
0x180004544  cmovl   ebp, esi
0x180004547  test    edx, edx
0x180004549  jle     short loc_1800045A9
0x18000454b  xor     ecx, ecx
0x18000454d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180004552  mov     rbx, rsi
0x180004555  shl     rbx, 4
0x180004559  call    cs:__imp_GetProcessHeap
0x180004560  nop     dword ptr [rax+rax+00h]
0x180004565  mov     r8, rbx; dwBytes
0x180004568  xor     edx, edx; dwFlags
0x18000456a  mov     rcx, rax; hHeap
0x18000456d  call    cs:__imp_HeapAlloc
0x180004574  nop     dword ptr [rax+rax+00h]
0x180004579  mov     rbx, rax
0x18000457c  test    rax, rax
0x18000457f  jnz     short loc_180004592
0x180004581  mov     edi, 8007000Eh
0x180004586  mov     ecx, edi
0x180004588  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000458d  jmp     loc_180004628
0x180004592  test    ebp, ebp
0x180004594  jz      short loc_1800045A9
0x180004596  mov     rdx, [rdi+8]; Src
0x18000459a  mov     rcx, rax; void *
0x18000459d  movsxd  r8, ebp
0x1800045a0  shl     r8, 4; Size
0x1800045a4  call    memcpy_0
0x1800045a9  mov     r15, rbx
0x1800045ac  mov     r12, rbx
0x1800045af  cmp     esi, [rdi+4]
0x1800045b2  jge     short loc_1800045E5
0x1800045b4  mov     ebx, esi
0x1800045b6  movsxd  r14, ebx
0x1800045b9  shl     r14, 4
0x1800045bd  add     r14, [rdi+8]
0x1800045c1  jz      short loc_1800045DE
0x1800045c3  mov     rcx, [r14]
0x1800045c6  test    rcx, rcx
0x1800045c9  jz      short loc_1800045DE
0x1800045cb  mov     rax, [rcx]
0x1800045ce  mov     rax, [rax+10h]
0x1800045d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045d7  mov     qword ptr [r14], 0
0x1800045de  inc     ebx
0x1800045e0  cmp     ebx, [rdi+4]
0x1800045e3  jl      short loc_1800045B6
0x1800045e5  mov     r14, [rdi+8]
0x1800045e9  xor     ebx, ebx
0x1800045eb  test    r14, r14
0x1800045ee  jz      short loc_180004614
0x1800045f0  call    cs:__imp_GetProcessHeap
0x1800045f7  nop     dword ptr [rax+rax+00h]
0x1800045fc  mov     r8, r14; lpMem
0x1800045ff  xor     edx, edx; dwFlags
0x180004601  mov     rcx, rax; hHeap
0x180004604  call    cs:__imp_HeapFree
0x18000460b  nop     dword ptr [rax+rax+00h]
0x180004610  mov     [rdi+8], rbx
0x180004614  xor     eax, eax
0x180004616  test    r15, r15
0x180004619  cmovnz  rax, r12
0x18000461d  mov     [rdi+8], rax
0x180004621  mov     [rdi+4], ebp
0x180004624  mov     [rdi], esi
0x180004626  xor     edi, edi
0x180004628  mov     ecx, edi
0x18000462a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000462f  test    rbx, rbx
0x180004632  jz      short loc_180004654
0x180004634  call    cs:__imp_GetProcessHeap
0x18000463b  nop     dword ptr [rax+rax+00h]
0x180004640  mov     r8, rbx; lpMem
0x180004643  xor     edx, edx; dwFlags
0x180004645  mov     rcx, rax; hHeap
0x180004648  call    cs:__imp_HeapFree
0x18000464f  nop     dword ptr [rax+rax+00h]
0x180004654  mov     eax, edi
0x180004656  add     rsp, 20h
0x18000465a  pop     r15
0x18000465c  pop     r14
0x18000465e  pop     r12
0x180004660  pop     rdi
0x180004661  pop     rsi
0x180004662  pop     rbp
0x180004663  pop     rbx
0x180004664  retn
```
