# ForEachElem<COMXProc::CAdviseClient,COMXProc::CSendNotifForEachAdvise>(CNamedElemList<COMXProc::CAdviseClient> *,COMXProc::CSendNotifForEachAdvise *,int)

- ea: `0x180002890`
- end: `0x180002b75`
- name: `??$ForEachElem@VCAdviseClient@COMXProc@@VCSendNotifForEachAdvise@2@@@YAJPEAV?$CNamedElemList@VCAdviseClient@COMXProc@@@@PEAVCSendNotifForEachAdvise@COMXProc@@H@Z`
- size: `741`
- prototype: `__int64 __fastcall(SIZE_T, unsigned int **)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180001530`
- `0x180001e80`

## callees

- `0x1800012c0`
- `0x180001330`
- `0x180002890`
- `0x180003570`
- `0x18001b404`
- `0x180028cf8`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!QueueUserAPC` at `0x180002a77`
- `api-ms-win-core-processthreads-l1-1-0!QueueUserAPC` at `0x180002a77`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800028f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002977`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800028f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002977`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000294e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800029e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002b49`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000294e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800029e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002b49`
- `api-ms-win-core-memory-l1-1-0!VirtualAllocEx` at `0x180002a2d`
- `api-ms-win-core-memory-l1-1-0!VirtualAllocEx` at `0x180002a2d`
- `api-ms-win-core-memory-l1-1-0!VirtualFreeEx` at `0x180002aa0`
- `api-ms-win-core-memory-l1-1-0!VirtualFreeEx` at `0x180002aa0`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180002a5b`
- `api-ms-win-core-memory-l1-1-0!WriteProcessMemory` at `0x180002a5b`

## pseudocode

```c
__int64 __fastcall ForEachElem<COMXProc::CAdviseClient,COMXProc::CSendNotifForEachAdvise>(SIZE_T a1, unsigned int **a2)
{
  CRefCounted *v2; // rbx
  _DWORD *v4; // rax
  _DWORD *v5; // rsi
  __int64 v6; // rdx
  struct _RTL_CRITICAL_SECTION *v7; // rcx
  int ValidTail; // r13d
  CRefCounted *v9; // rdi
  __int64 v10; // rdx
  struct _RTL_CRITICAL_SECTION *v11; // rcx
  __int64 v12; // rdx
  int v13; // edi
  __int64 v14; // r14
  struct _RTL_CRITICAL_SECTION *v15; // rcx
  __int64 v16; // rbx
  __int64 v17; // rdx
  struct _RTL_CRITICAL_SECTION *v18; // rcx
  unsigned int *v19; // rbx
  unsigned int v20; // eax
  int v21; // ecx
  SIZE_T v22; // rdi
  __int64 v23; // rcx
  void *v24; // rbp
  void *v25; // rcx
  int v26; // edi
  __int64 v28; // rdx
  struct _RTL_CRITICAL_SECTION *v29; // rcx
  SIZE_T NumberOfBytesWritten; // [rsp+70h] [rbp+8h] BYREF

  NumberOfBytesWritten = a1;
  v2 = COMXProc::g_pnelAdviseClient;
  v4 = operator new(0x28u);
  v5 = v4;
  if ( !v4 )
    return 2147942414LL;
  v4[2] = 1;
  *((_QWORD *)v4 + 2) = 0;
  *(_QWORD *)v4 = &CNamedElemEnum<COMXProc::CAdviseClient>::`vftable';
  *((_QWORD *)v4 + 4) = 0;
  v6 = *((_QWORD *)v2 + 3);
  NumberOfBytesWritten = 0;
  v7 = (struct _RTL_CRITICAL_SECTION *)(v6 + 8);
  if ( !v6 )
    v7 = 0;
  EnterCriticalSection(v7);
  ValidTail = CNamedElemList<COMXProc::CAdviseClient>::_GetValidTail(v2, &NumberOfBytesWritten);
  if ( ValidTail < 0 )
    goto LABEL_45;
  v9 = (CRefCounted *)NumberOfBytesWritten;
  ValidTail = CNamedElemEnum<COMXProc::CAdviseClient>::_Init(v5, NumberOfBytesWritten, *((_QWORD *)v2 + 3));
  if ( ValidTail < 0 )
  {
    CRefCounted::Release(v9);
LABEL_45:
    (**(void (__fastcall ***)(_DWORD *, __int64))v5)(v5, 1);
    v28 = *((_QWORD *)v2 + 3);
    v29 = (struct _RTL_CRITICAL_SECTION *)(v28 + 8);
    if ( !v28 )
      v29 = 0;
    LeaveCriticalSection(v29);
    return (unsigned int)ValidTail;
  }
  CRefCounted::Release(v9);
  v10 = *((_QWORD *)v2 + 3);
  v11 = (struct _RTL_CRITICAL_SECTION *)(v10 + 8);
  if ( !v10 )
    v11 = 0;
  LeaveCriticalSection(v11);
  while ( 1 )
  {
    v12 = *((_QWORD *)v5 + 4);
    v13 = 1;
    v14 = 0;
    v15 = (struct _RTL_CRITICAL_SECTION *)(v12 + 8);
    if ( !v12 )
      v15 = 0;
    EnterCriticalSection(v15);
    v16 = *((_QWORD *)v5 + 2);
    if ( v16 )
    {
      if ( v5[6] && *(_QWORD *)(v16 + 16) )
        goto LABEL_20;
      v16 = *(_QWORD *)(v16 + 24);
      if ( v16 )
      {
        while ( !*(_QWORD *)(v16 + 16) )
        {
          v16 = *(_QWORD *)(v16 + 24);
          if ( !v16 )
            goto LABEL_19;
        }
        _InterlockedIncrement((volatile signed __int32 *)(v16 + 8));
      }
LABEL_19:
      CRefCounted::Release(*((CRefCounted **)v5 + 2));
      *((_QWORD *)v5 + 2) = v16;
      if ( v16 )
      {
LABEL_20:
        _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v16 + 16) + 8LL));
        v14 = *(_QWORD *)(v16 + 16);
        v13 = 0;
      }
      v5[6] = 0;
    }
    v17 = *((_QWORD *)v5 + 4);
    v18 = (struct _RTL_CRITICAL_SECTION *)(v17 + 8);
    if ( !v17 )
      v18 = 0;
    LeaveCriticalSection(v18);
    if ( v13 == 1 )
      break;
    v19 = *a2;
    v20 = (*a2)[2];
    if ( !v20 || (v21 = *(_DWORD *)(v14 + 48)) == 0 || v21 == v20 )
    {
      v22 = *v19;
      v24 = VirtualAllocEx(*(HANDLE *)(v14 + 32), 0, v22, 0x103000u, 4u);
      if ( v24 )
      {
        v25 = *(void **)(v14 + 32);
        NumberOfBytesWritten = 0;
        if ( WriteProcessMemory(v25, v24, v19, (unsigned int)v22, &NumberOfBytesWritten) && NumberOfBytesWritten == v22 )
        {
          v26 = 0;
          if ( !QueueUserAPC(*(PAPCFUNC *)(v14 + 24), *(HANDLE *)(v14 + 40), (ULONG_PTR)v24) )
            v26 = -2147467259;
        }
        else
        {
          v26 = -2147467259;
          VirtualFreeEx(*(HANDLE *)(v14 + 32), v24, 0, 0x8000u);
        }
      }
      else
      {
        v26 = -2147024882;
      }
      if ( v26 < 0 )
        CNamedElemList<COMXProc::CAdviseClient>::Remove<unsigned long>(v23, *(unsigned int *)(v14 + 16));
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v14 + 8), 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(__int64, __int64))v14)(v14, 1);
  }
  if ( _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
    (**(void (__fastcall ***)(_DWORD *, __int64))v5)(v5, 1);
  return 1;
}

```

## disassembly

```asm
0x180002890  mov     [rsp+NumberOfBytesWritten], rcx
0x180002895  push    rbx
0x180002896  push    rbp
0x180002897  push    rsi
0x180002898  push    rdi
0x180002899  push    r12
0x18000289b  push    r13
0x18000289d  sub     rsp, 38h
0x1800028a1  mov     rbx, cs:?g_pnelAdviseClient@COMXProc@@3PEAV?$CNamedElemList@VCAdviseClient@COMXProc@@@@EA; CNamedElemList<COMXProc::CAdviseClient> * COMXProc::g_pnelAdviseClient
0x1800028a8  mov     ecx, 28h ; '('; Size
0x1800028ad  mov     r12, rdx
0x1800028b0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800028b5  mov     rsi, rax
0x1800028b8  test    rax, rax
0x1800028bb  jz      loc_180002B5F
0x1800028c1  xor     ebp, ebp
0x1800028c3  mov     dword ptr [rax+8], 1
0x1800028ca  lea     rax, ??_7?$CNamedElemEnum@VCAdviseClient@COMXProc@@@@6B@; const CNamedElemEnum<COMXProc::CAdviseClient>::`vftable'
0x1800028d1  mov     [rsi+10h], rbp
0x1800028d5  mov     [rsi], rax
0x1800028d8  mov     [rsi+20h], rbp
0x1800028dc  mov     rdx, [rbx+18h]
0x1800028e0  test    rdx, rdx
0x1800028e3  mov     [rsp+68h+NumberOfBytesWritten], rbp
0x1800028e8  lea     rcx, [rdx+8]
0x1800028ec  cmovz   rcx, rbp; lpCriticalSection
0x1800028f0  call    cs:__imp_EnterCriticalSection
0x1800028f6  lea     rdx, [rsp+68h+NumberOfBytesWritten]
0x1800028fb  mov     rcx, rbx
0x1800028fe  call    ?_GetValidTail@?$CNamedElemList@VCAdviseClient@COMXProc@@@@AEAAJPEAPEAV?$CElemSlot@VCAdviseClient@COMXProc@@@@@Z; CNamedElemList<COMXProc::CAdviseClient>::_GetValidTail(CElemSlot<COMXProc::CAdviseClient> * *)
0x180002903  mov     r13d, eax
0x180002906  test    eax, eax
0x180002908  js      loc_180002B27
0x18000290e  mov     rdi, [rsp+68h+NumberOfBytesWritten]
0x180002913  mov     rcx, rsi
0x180002916  mov     r8, [rbx+18h]
0x18000291a  mov     rdx, rdi
0x18000291d  call    ?_Init@?$CNamedElemEnum@VCAdviseClient@COMXProc@@@@QEAAJPEAV?$CElemSlot@VCAdviseClient@COMXProc@@@@PEAV?$CRefCountedCritSectWithResource@V?$CNamedElemList@VCAdviseClient@COMXProc@@@@@@@Z; CNamedElemEnum<COMXProc::CAdviseClient>::_Init(CElemSlot<COMXProc::CAdviseClient> *,CRefCountedCritSectWithResource<CNamedElemList<COMXProc::CAdviseClient>> *)
0x180002922  mov     r13d, eax
0x180002925  mov     rcx, rdi; this
0x180002928  test    eax, eax
0x18000292a  js      loc_180002B22
0x180002930  mov     [rsp+68h+arg_8], r14
0x180002935  mov     [rsp+68h+var_38], r15
0x18000293a  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x18000293f  mov     rdx, [rbx+18h]
0x180002943  test    rdx, rdx
0x180002946  lea     rcx, [rdx+8]
0x18000294a  cmovz   rcx, rbp; lpCriticalSection
0x18000294e  call    cs:__imp_LeaveCriticalSection
0x180002954  mov     r13d, 8007000Eh
0x18000295a  mov     r15d, 0FFFFFFFFh
0x180002960  mov     rdx, [rsi+20h]
0x180002964  mov     edi, 1
0x180002969  test    rdx, rdx
0x18000296c  mov     r14, rbp
0x18000296f  lea     rcx, [rdx+8]
0x180002973  cmovz   rcx, rbp; lpCriticalSection
0x180002977  call    cs:__imp_EnterCriticalSection
0x18000297d  mov     rbx, [rsi+10h]
0x180002981  test    rbx, rbx
0x180002984  jz      short loc_1800029D9
0x180002986  cmp     dword ptr [rsi+18h], 0
0x18000298a  jz      short loc_180002993
0x18000298c  cmp     qword ptr [rbx+10h], 0
0x180002991  jnz     short loc_1800029C8
0x180002993  mov     rbx, [rbx+18h]
0x180002997  test    rbx, rbx
0x18000299a  jz      short loc_1800029B6
0x18000299c  nop     dword ptr [rax+00h]
0x1800029a0  cmp     qword ptr [rbx+10h], 0
0x1800029a5  jnz     short loc_1800029B2
0x1800029a7  mov     rbx, [rbx+18h]
0x1800029ab  test    rbx, rbx
0x1800029ae  jnz     short loc_1800029A0
0x1800029b0  jmp     short loc_1800029B6
0x1800029b2  lock inc dword ptr [rbx+8]
0x1800029b6  mov     rcx, [rsi+10h]; this
0x1800029ba  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x1800029bf  mov     [rsi+10h], rbx
0x1800029c3  test    rbx, rbx
0x1800029c6  jz      short loc_1800029D6
0x1800029c8  mov     rax, [rbx+10h]
0x1800029cc  lock inc dword ptr [rax+8]
0x1800029d0  mov     r14, [rbx+10h]
0x1800029d4  mov     edi, ebp
0x1800029d6  mov     [rsi+18h], ebp
0x1800029d9  mov     rdx, [rsi+20h]
0x1800029dd  test    rdx, rdx
0x1800029e0  lea     rcx, [rdx+8]
0x1800029e4  cmovz   rcx, rbp; lpCriticalSection
0x1800029e8  call    cs:__imp_LeaveCriticalSection
0x1800029ee  cmp     edi, 1
0x1800029f1  jz      loc_180002AEA
0x1800029f7  mov     rbx, [r12]
0x1800029fb  mov     eax, [rbx+8]
0x1800029fe  test    eax, eax
0x180002a00  jz      short loc_180002A14
0x180002a02  mov     ecx, [r14+30h]
0x180002a06  test    ecx, ecx
0x180002a08  jz      short loc_180002A14
0x180002a0a  mov     edi, ebp
0x180002a0c  cmp     ecx, eax
0x180002a0e  jnz     loc_180002ABE
0x180002a14  mov     edi, [rbx]
0x180002a16  mov     r9d, 103000h; flAllocationType
0x180002a1c  mov     rcx, [r14+20h]; hProcess
0x180002a20  mov     r8d, edi; dwSize
0x180002a23  xor     edx, edx; lpAddress
0x180002a25  mov     [rsp+68h+flProtect], 4; flProtect
0x180002a2d  call    cs:__imp_VirtualAllocEx
0x180002a33  mov     rbp, rax
0x180002a36  test    rax, rax
0x180002a39  jz      short loc_180002AA8
0x180002a3b  mov     rcx, [r14+20h]; hProcess
0x180002a3f  lea     rax, [rsp+68h+NumberOfBytesWritten]
0x180002a44  mov     r9d, edi; nSize
0x180002a47  mov     qword ptr [rsp+68h+flProtect], rax; lpNumberOfBytesWritten
0x180002a4c  mov     r8, rbx; lpBuffer
0x180002a4f  mov     [rsp+68h+NumberOfBytesWritten], 0
0x180002a58  mov     rdx, rbp; lpBaseAddress
0x180002a5b  call    cs:__imp_WriteProcessMemory
0x180002a61  test    eax, eax
0x180002a63  jz      short loc_180002A8B
0x180002a65  cmp     [rsp+68h+NumberOfBytesWritten], rdi
0x180002a6a  jnz     short loc_180002A8B
0x180002a6c  mov     rdx, [r14+28h]; hThread
0x180002a70  mov     r8, rbp; dwData
0x180002a73  mov     rcx, [r14+18h]; pfnAPC
0x180002a77  call    cs:__imp_QueueUserAPC
0x180002a7d  xor     edi, edi
0x180002a7f  test    eax, eax
0x180002a81  mov     eax, 80004005h
0x180002a86  cmovz   edi, eax
0x180002a89  jmp     short loc_180002AAB
0x180002a8b  mov     rcx, [r14+20h]; hProcess
0x180002a8f  mov     r9d, 8000h; dwFreeType
0x180002a95  xor     r8d, r8d; dwSize
0x180002a98  mov     rdx, rbp; lpAddress
0x180002a9b  mov     edi, 80004005h
0x180002aa0  call    cs:__imp_VirtualFreeEx
0x180002aa6  jmp     short loc_180002AAB
0x180002aa8  mov     edi, r13d
0x180002aab  test    edi, edi
0x180002aad  jns     short loc_180002ABE
0x180002aaf  mov     edx, [r14+10h]
0x180002ab3  call    ??$Remove@K@?$CNamedElemList@VCAdviseClient@COMXProc@@@@QEAAJK@Z; CNamedElemList<COMXProc::CAdviseClient>::Remove<ulong>(ulong)
0x180002ab8  xor     ebp, ebp
0x180002aba  mov     edi, ebp
0x180002abc  jmp     short loc_180002AC0
0x180002abe  xor     ebp, ebp
0x180002ac0  mov     eax, r15d
0x180002ac3  lock xadd [r14+8], eax
0x180002ac9  cmp     eax, 1
0x180002acc  jnz     short loc_180002AE1
0x180002ace  mov     rax, [r14]
0x180002ad1  mov     edx, 1
0x180002ad6  mov     rcx, r14
0x180002ad9  mov     rax, [rax]
0x180002adc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ae1  cmp     edi, 1
0x180002ae4  jnz     loc_180002960
0x180002aea  mov     r14, [rsp+68h+arg_8]
0x180002aef  lock xadd [rsi+8], r15d
0x180002af5  cmp     r15d, 1
0x180002af9  mov     r15, [rsp+68h+var_38]
0x180002afe  jnz     short loc_180002B13
0x180002b00  mov     r8, [rsi]
0x180002b03  mov     edx, 1
0x180002b08  mov     rcx, rsi
0x180002b0b  mov     rax, [r8]
0x180002b0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b13  mov     eax, edi
0x180002b15  add     rsp, 38h
0x180002b19  pop     r13
0x180002b1b  pop     r12
0x180002b1d  pop     rdi
0x180002b1e  pop     rsi
0x180002b1f  pop     rbp
0x180002b20  pop     rbx
0x180002b21  retn
0x180002b22  call    ?Release@CRefCounted@@QEBAKXZ; CRefCounted::Release(void)
0x180002b27  mov     rax, [rsi]
0x180002b2a  mov     edx, 1
0x180002b2f  mov     rcx, rsi
0x180002b32  mov     rax, [rax]
0x180002b35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b3a  mov     rdx, [rbx+18h]
0x180002b3e  test    rdx, rdx
0x180002b41  lea     rcx, [rdx+8]
0x180002b45  cmovz   rcx, rbp; lpCriticalSection
0x180002b49  call    cs:__imp_LeaveCriticalSection
0x180002b4f  mov     eax, r13d
0x180002b52  add     rsp, 38h
0x180002b56  pop     r13
0x180002b58  pop     r12
0x180002b5a  pop     rdi
0x180002b5b  pop     rsi
0x180002b5c  pop     rbp
0x180002b5d  pop     rbx
0x180002b5e  retn
0x180002b5f  mov     r13d, 8007000Eh
0x180002b65  mov     eax, r13d
0x180002b68  add     rsp, 38h
0x180002b6c  pop     r13
0x180002b6e  pop     r12
0x180002b70  pop     rdi
0x180002b71  pop     rsi
0x180002b72  pop     rbp
0x180002b73  pop     rbx
0x180002b74  retn
```
