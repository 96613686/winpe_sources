# TLPCMgr::ProcessPortShutdown(void *,int *)

- ea: `0x140011814`
- end: `0x140011ba7`
- name: `?ProcessPortShutdown@TLPCMgr@@QEAAKPEAXPEAH@Z`
- size: `915`
- prototype: `unsigned int __fastcall(TLPCMgr *__hidden this, void *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x140012390`

## callees

- `0x140001b90`
- `0x140006894`
- `0x1400085d8`
- `0x1400086e0`
- `0x140011268`
- `0x140011814`
- `0x140012254`
- `0x140016010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1400118bc`
- `KERNEL32!EnterCriticalSection` at `0x140011933`
- `KERNEL32!EnterCriticalSection` at `0x140011979`
- `KERNEL32!EnterCriticalSection` at `0x140011a8f`
- `KERNEL32!EnterCriticalSection` at `0x1400118bc`
- `KERNEL32!EnterCriticalSection` at `0x140011933`
- `KERNEL32!EnterCriticalSection` at `0x140011979`
- `KERNEL32!EnterCriticalSection` at `0x140011a8f`
- `KERNEL32!LeaveCriticalSection` at `0x1400118e5`
- `KERNEL32!LeaveCriticalSection` at `0x14001195f`
- `KERNEL32!LeaveCriticalSection` at `0x140011a40`
- `KERNEL32!LeaveCriticalSection` at `0x140011b61`
- `KERNEL32!LeaveCriticalSection` at `0x1400118e5`
- `KERNEL32!LeaveCriticalSection` at `0x14001195f`
- `KERNEL32!LeaveCriticalSection` at `0x140011a40`
- `KERNEL32!LeaveCriticalSection` at `0x140011b61`
- `WINSPOOL!ClosePrinter` at `0x1400118f7`
- `WINSPOOL!ClosePrinter` at `0x1400118f7`
- `ntdll!NtClose` at `0x140011a6a`
- `ntdll!NtClose` at `0x140011a6a`
- `ntdll!NtAlpcDeleteSectionView` at `0x140011a61`
- `ntdll!NtAlpcDeleteSectionView` at `0x140011a61`

## pseudocode

```c
__int64 __fastcall TLPCMgr::ProcessPortShutdown(TLPCMgr *this, _QWORD *a2, int *a3)
{
  signed __int32 v6; // et0
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rsi
  unsigned int v10; // r14d
  void *v11; // r15
  int v12; // r13d
  int v13; // edi
  __int64 v14; // rbp
  __int64 v15; // rbx
  __int64 *v16; // rax
  int i; // edx
  int v18; // r12d
  _QWORD *j; // rbx
  __int64 v20; // rdi
  __int64 v21; // rdi
  _QWORD *v22; // rcx
  _QWORD *v23; // rbx
  __int64 v24; // rsi
  __int64 v25; // rax
  __int64 v26; // rax
  bool v27; // zf
  __int64 v28; // rdi
  _QWORD *v29; // rcx
  __int64 v30; // rdx
  _QWORD *v31; // rbx
  __int64 v32; // rsi
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v36; // [rsp+20h] [rbp-58h]
  HANDLE v38; // [rsp+88h] [rbp+10h] BYREF
  __int64 v39; // [rsp+90h] [rbp+18h]
  __int64 v40; // [rsp+98h] [rbp+20h] BYREF

  v39 = a2[6];
  v40 = v39;
  v36 = a2[12];
  SplWow64Telemetry::WriteDbgTraceInfo("TLPCMgr::ProcessPortShutdown", L"Processing port shutdown.");
  v6 = _InterlockedAdd((volatile signed __int32 *)(a2[13] + 96LL), 0xFFFFFFFF);
  v7 = *((_QWORD *)this + 10);
  *a3 = v6 == 0;
  v8 = TLstMgr<TLPCMgr::TPrinterHandleInfo,void *>::ElementInList(v7, &v40);
  v9 = v8;
  if ( !v8 )
  {
    v10 = 87;
    SplWow64Telemetry::WriteDbgTraceError(
      "TLPCMgr::ProcessPortShutdown",
      L"Failed to process port closure.  Error %d.",
      87);
    return v10;
  }
  v10 = 0;
  v11 = (void *)a2[7];
  v12 = 0;
  if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v8 + 32LL) + 48LL) > 1u )
  {
    v18 = 0;
  }
  else
  {
    v13 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v8 + 40LL) + 48LL);
    do
    {
      if ( !v13 )
        break;
      v14 = 0;
      v15 = *(_QWORD *)(*(_QWORD *)v9 + 40LL);
      EnterCriticalSection((LPCRITICAL_SECTION)(v15 + 56));
      if ( *(_DWORD *)(v15 + 48) )
      {
        v16 = *(__int64 **)(v15 + 32);
        for ( i = 0; v16 && !i; i = 1 )
        {
          v14 = *v16;
          v16 = (__int64 *)v16[1];
        }
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(v15 + 56));
      v38 = *(HANDLE *)(v14 + 24);
      v10 = ClosePrinter(v38);
      TLstMgr<TLPCMgr::TPrinterHandleInfo,void *>::RmvElemFromList(*(_QWORD *)(*(_QWORD *)v9 + 40LL), &v38);
      --v13;
    }
    while ( !v10 );
    v18 = 1;
  }
  j = 0;
  v20 = *(_QWORD *)(*(_QWORD *)v9 + 32LL);
  EnterCriticalSection((LPCRITICAL_SECTION)(v20 + 56));
  if ( *(_DWORD *)(v20 + 48) )
  {
    for ( j = *(_QWORD **)(v20 + 32); j && *j && *(void **)(*j + 56LL) != v11; j = (_QWORD *)j[1] )
      ;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v20 + 56));
  if ( j )
  {
    v21 = *(_QWORD *)(*(_QWORD *)v9 + 32LL);
    EnterCriticalSection((LPCRITICAL_SECTION)(v21 + 56));
    if ( !*(_DWORD *)(v21 + 48) )
    {
LABEL_39:
      LeaveCriticalSection((LPCRITICAL_SECTION)(v21 + 56));
      if ( v36 )
        NtAlpcDeleteSectionView(*((_QWORD *)this + 8), 0, v36);
      NtClose(v11);
      v12 = 1;
      goto LABEL_42;
    }
    v22 = *(_QWORD **)(v21 + 40);
    if ( v22 && *(void **)(*v22 + 56LL) == v11 )
    {
      v23 = *(_QWORD **)(v21 + 40);
      v24 = v21 + 32;
    }
    else
    {
      v24 = v21 + 32;
      v23 = *(_QWORD **)(v21 + 32);
      if ( !v23 )
        goto LABEL_26;
      while ( *(void **)(*v23 + 56LL) != v11 )
      {
LABEL_26:
        v23 = (_QWORD *)v23[1];
        if ( !v23 )
          goto LABEL_39;
      }
      if ( v23 != v22 )
      {
        if ( *(_QWORD **)v24 == v23 )
        {
          v26 = *(_QWORD *)(*(_QWORD *)v24 + 8LL);
          *(_QWORD *)v24 = v26;
          if ( v26 )
            *(_QWORD *)(v26 + 16) = 0;
        }
        else
        {
          *(_QWORD *)(v23[2] + 8LL) = v23[1];
          *(_QWORD *)(v23[1] + 16LL) = v23[2];
        }
        goto LABEL_35;
      }
    }
    v25 = v22[2];
    *(_QWORD *)(v21 + 40) = v25;
    if ( v25 )
      *(_QWORD *)(v25 + 8) = 0;
LABEL_35:
    if ( *v23 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v23 + 16LL))(*v23);
    operator delete(v23);
    v27 = (*(_DWORD *)(v21 + 48))-- == 1;
    if ( v27 )
    {
      *(_QWORD *)(v21 + 40) = 0;
      *(_QWORD *)v24 = 0;
    }
    goto LABEL_39;
  }
LABEL_42:
  if ( !v18 )
    goto LABEL_63;
  v28 = *((_QWORD *)this + 10);
  EnterCriticalSection((LPCRITICAL_SECTION)(v28 + 56));
  if ( *(_DWORD *)(v28 + 48) )
  {
    v29 = *(_QWORD **)(v28 + 40);
    v30 = v39;
    if ( v29 && *(_QWORD *)(*v29 + 24LL) == v39 )
    {
      v31 = *(_QWORD **)(v28 + 40);
      v32 = v28 + 32;
    }
    else
    {
      v32 = v28 + 32;
      v31 = *(_QWORD **)(v28 + 32);
      if ( !v31 )
        goto LABEL_49;
      while ( *(_QWORD *)(*v31 + 24LL) != v39 )
      {
LABEL_49:
        v31 = (_QWORD *)v31[1];
        if ( !v31 )
          goto LABEL_62;
      }
      if ( v31 != v29 )
      {
        if ( *(_QWORD **)v32 == v31 )
        {
          v34 = *(_QWORD *)(*(_QWORD *)v32 + 8LL);
          *(_QWORD *)v32 = v34;
          if ( v34 )
            *(_QWORD *)(v34 + 16) = 0;
        }
        else
        {
          *(_QWORD *)(v31[2] + 8LL) = v31[1];
          *(_QWORD *)(v31[1] + 16LL) = v31[2];
        }
        goto LABEL_58;
      }
    }
    v33 = v29[2];
    *(_QWORD *)(v28 + 40) = v33;
    if ( v33 )
      *(_QWORD *)(v33 + 8) = 0;
LABEL_58:
    if ( *v31 )
      (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v31 + 16LL))(*v31, v30);
    operator delete(v31);
    v27 = (*(_DWORD *)(v28 + 48))-- == 1;
    if ( v27 )
    {
      *(_QWORD *)(v28 + 40) = 0;
      *(_QWORD *)v32 = 0;
    }
  }
LABEL_62:
  LeaveCriticalSection((LPCRITICAL_SECTION)(v28 + 56));
LABEL_63:
  if ( v12 )
    TLoad64BitDllsMgr::DecUIRefCnt(*((TLoad64BitDllsMgr **)this + 6));
  return v10;
}

```

## disassembly

```asm
0x140011814  mov     r11, rsp
0x140011817  mov     [r11+8], rcx
0x14001181b  push    rbx
0x14001181c  push    rbp
0x14001181d  push    rsi
0x14001181e  push    rdi
0x14001181f  push    r12
0x140011821  push    r13
0x140011823  push    r14
0x140011825  push    r15
0x140011827  sub     rsp, 38h
0x14001182b  mov     rax, [rdx+30h]
0x14001182f  mov     rdi, rdx
0x140011832  mov     [r11+18h], rax
0x140011836  mov     rsi, rcx
0x140011839  mov     [r11+20h], rax
0x14001183d  lea     rcx, aTlpcmgrProcess_0; "TLPCMgr::ProcessPortShutdown"
0x140011844  mov     rax, [rdx+60h]
0x140011848  mov     rbx, r8
0x14001184b  lea     rdx, aProcessingPort; "Processing port shutdown."
0x140011852  mov     [rsp+78h+var_58], rax
0x140011857  call    ?WriteDbgTraceInfo@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14001185c  mov     r9, [rdi+68h]
0x140011860  lock add dword ptr [r9+60h], 0FFFFFFFFh
0x140011866  mov     rcx, [rsi+50h]
0x14001186a  lea     rdx, [rsp+78h+arg_18]
0x140011872  mov     eax, 0
0x140011877  setz    al
0x14001187a  mov     [rbx], eax
0x14001187c  call    ?ElementInList@?$TLstMgr@VTPrinterHandleInfo@TLPCMgr@@PEAX@@QEBAPEAV?$TLstNd@VTPrinterHandleInfo@TLPCMgr@@PEAX@@AEBQEAX@Z; TLstMgr<TLPCMgr::TPrinterHandleInfo,void *>::ElementInList(void * const &)
0x140011881  mov     rsi, rax
0x140011884  test    rax, rax
0x140011887  jz      loc_140011B77
0x14001188d  mov     rdx, [rax]
0x140011890  xor     r14d, r14d
0x140011893  mov     r15, [rdi+38h]
0x140011897  xor     r13d, r13d
0x14001189a  mov     rcx, [rdx+20h]
0x14001189e  cmp     dword ptr [rcx+30h], 1
0x1400118a2  ja      short loc_140011923
0x1400118a4  mov     rcx, [rdx+28h]
0x1400118a8  mov     edi, [rcx+30h]
0x1400118ab  test    edi, edi
0x1400118ad  jz      short loc_14001191B
0x1400118af  mov     rax, [rsi]
0x1400118b2  xor     ebp, ebp
0x1400118b4  mov     rbx, [rax+28h]
0x1400118b8  lea     rcx, [rbx+38h]; lpCriticalSection
0x1400118bc  call    cs:__imp_EnterCriticalSection
0x1400118c2  cmp     [rbx+30h], ebp
0x1400118c5  jz      short loc_1400118E1
0x1400118c7  mov     rax, [rbx+20h]
0x1400118cb  xor     edx, edx
0x1400118cd  jmp     short loc_1400118DC
0x1400118cf  test    edx, edx
0x1400118d1  jnz     short loc_1400118E1
0x1400118d3  mov     rbp, [rax]
0x1400118d6  inc     edx
0x1400118d8  mov     rax, [rax+8]
0x1400118dc  test    rax, rax
0x1400118df  jnz     short loc_1400118CF
0x1400118e1  lea     rcx, [rbx+38h]; lpCriticalSection
0x1400118e5  call    cs:__imp_LeaveCriticalSection
0x1400118eb  mov     rcx, [rbp+18h]; hPrinter
0x1400118ef  mov     [rsp+78h+arg_8], rcx
0x1400118f7  call    cs:__imp_ClosePrinter
0x1400118fd  mov     rcx, [rsi]
0x140011900  lea     rdx, [rsp+78h+arg_8]
0x140011908  mov     r14d, eax
0x14001190b  mov     rcx, [rcx+28h]
0x14001190f  call    ?RmvElemFromList@?$TLstMgr@VTPrinterHandleInfo@TLPCMgr@@PEAX@@QEAAJAEBQEAX@Z; TLstMgr<TLPCMgr::TPrinterHandleInfo,void *>::RmvElemFromList(void * const &)
0x140011914  dec     edi
0x140011916  test    r14d, r14d
0x140011919  jz      short loc_1400118AB
0x14001191b  mov     r12d, 1
0x140011921  jmp     short loc_140011926
0x140011923  xor     r12d, r12d
0x140011926  mov     rax, [rsi]
0x140011929  xor     ebx, ebx
0x14001192b  mov     rdi, [rax+20h]
0x14001192f  lea     rcx, [rdi+38h]; lpCriticalSection
0x140011933  call    cs:__imp_EnterCriticalSection
0x140011939  cmp     [rdi+30h], ebx
0x14001193c  jz      short loc_14001195B
0x14001193e  mov     rbx, [rdi+20h]
0x140011942  jmp     short loc_140011956
0x140011944  mov     rax, [rbx]
0x140011947  test    rax, rax
0x14001194a  jz      short loc_14001195B
0x14001194c  cmp     [rax+38h], r15
0x140011950  jz      short loc_14001195B
0x140011952  mov     rbx, [rbx+8]
0x140011956  test    rbx, rbx
0x140011959  jnz     short loc_140011944
0x14001195b  lea     rcx, [rdi+38h]; lpCriticalSection
0x14001195f  call    cs:__imp_LeaveCriticalSection
0x140011965  test    rbx, rbx
0x140011968  jz      loc_140011A76
0x14001196e  mov     rax, [rsi]
0x140011971  mov     rdi, [rax+20h]
0x140011975  lea     rcx, [rdi+38h]; lpCriticalSection
0x140011979  call    cs:__imp_EnterCriticalSection
0x14001197f  cmp     [rdi+30h], r13d
0x140011983  jz      loc_140011A3C
0x140011989  mov     rcx, [rdi+28h]
0x14001198d  test    rcx, rcx
0x140011990  jz      short loc_1400119A4
0x140011992  mov     rax, [rcx]
0x140011995  cmp     [rax+38h], r15
0x140011999  jnz     short loc_1400119A4
0x14001199b  mov     rbx, rcx
0x14001199e  lea     rsi, [rdi+20h]
0x1400119a2  jmp     short loc_1400119C9
0x1400119a4  lea     rsi, [rdi+20h]
0x1400119a8  mov     rbx, [rsi]
0x1400119ab  test    rbx, rbx
0x1400119ae  jz      short loc_1400119B9
0x1400119b0  mov     rax, [rbx]
0x1400119b3  cmp     [rax+38h], r15
0x1400119b7  jz      short loc_1400119C4
0x1400119b9  mov     rbx, [rbx+8]
0x1400119bd  test    rbx, rbx
0x1400119c0  jnz     short loc_1400119B0
0x1400119c2  jmp     short loc_140011A3C
0x1400119c4  cmp     rbx, rcx
0x1400119c7  jnz     short loc_1400119DC
0x1400119c9  mov     rax, [rcx+10h]
0x1400119cd  mov     [rdi+28h], rax
0x1400119d1  test    rax, rax
0x1400119d4  jz      short loc_140011A0E
0x1400119d6  mov     [rax+8], r13
0x1400119da  jmp     short loc_140011A0E
0x1400119dc  mov     rax, [rsi]
0x1400119df  cmp     rax, rbx
0x1400119e2  jnz     short loc_1400119F6
0x1400119e4  mov     rax, [rax+8]
0x1400119e8  mov     [rsi], rax
0x1400119eb  test    rax, rax
0x1400119ee  jz      short loc_140011A0E
0x1400119f0  mov     [rax+10h], r13
0x1400119f4  jmp     short loc_140011A0E
0x1400119f6  mov     rcx, [rbx+10h]
0x1400119fa  mov     rax, [rbx+8]
0x1400119fe  mov     [rcx+8], rax
0x140011a02  mov     rcx, [rbx+8]
0x140011a06  mov     rax, [rbx+10h]
0x140011a0a  mov     [rcx+10h], rax
0x140011a0e  mov     rcx, [rbx]
0x140011a11  test    rcx, rcx
0x140011a14  jz      short loc_140011A22
0x140011a16  mov     rax, [rcx]
0x140011a19  mov     rax, [rax+10h]
0x140011a1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011a22  mov     edx, 18h
0x140011a27  mov     rcx, rbx; Block
0x140011a2a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140011a2f  add     dword ptr [rdi+30h], 0FFFFFFFFh
0x140011a33  jnz     short loc_140011A3C
0x140011a35  mov     [rdi+28h], r13
0x140011a39  mov     [rsi], r13
0x140011a3c  lea     rcx, [rdi+38h]; lpCriticalSection
0x140011a40  call    cs:__imp_LeaveCriticalSection
0x140011a46  mov     rax, [rsp+78h+var_58]
0x140011a4b  test    rax, rax
0x140011a4e  jz      short loc_140011A67
0x140011a50  mov     rcx, [rsp+78h+arg_0]
0x140011a58  mov     r8, rax
0x140011a5b  xor     edx, edx
0x140011a5d  mov     rcx, [rcx+40h]
0x140011a61  call    cs:__imp_NtAlpcDeleteSectionView
0x140011a67  mov     rcx, r15; Handle
0x140011a6a  call    cs:__imp_NtClose
0x140011a70  mov     r13d, 1
0x140011a76  mov     r15, [rsp+78h+arg_0]
0x140011a7e  test    r12d, r12d
0x140011a81  jz      loc_140011B67
0x140011a87  mov     rdi, [r15+50h]
0x140011a8b  lea     rcx, [rdi+38h]; lpCriticalSection
0x140011a8f  call    cs:__imp_EnterCriticalSection
0x140011a95  xor     r12d, r12d
0x140011a98  cmp     [rdi+30h], r12d
0x140011a9c  jz      loc_140011B5D
0x140011aa2  mov     rcx, [rdi+28h]
0x140011aa6  mov     rdx, [rsp+78h+arg_10]
0x140011aae  test    rcx, rcx
0x140011ab1  jz      short loc_140011AC5
0x140011ab3  mov     rax, [rcx]
0x140011ab6  cmp     [rax+18h], rdx
0x140011aba  jnz     short loc_140011AC5
0x140011abc  mov     rbx, rcx
0x140011abf  lea     rsi, [rdi+20h]
0x140011ac3  jmp     short loc_140011AEA
0x140011ac5  lea     rsi, [rdi+20h]
0x140011ac9  mov     rbx, [rsi]
0x140011acc  test    rbx, rbx
0x140011acf  jz      short loc_140011ADA
0x140011ad1  mov     rax, [rbx]
0x140011ad4  cmp     [rax+18h], rdx
0x140011ad8  jz      short loc_140011AE5
0x140011ada  mov     rbx, [rbx+8]
0x140011ade  test    rbx, rbx
0x140011ae1  jnz     short loc_140011AD1
0x140011ae3  jmp     short loc_140011B5D
0x140011ae5  cmp     rbx, rcx
0x140011ae8  jnz     short loc_140011AFD
0x140011aea  mov     rax, [rcx+10h]
0x140011aee  mov     [rdi+28h], rax
0x140011af2  test    rax, rax
0x140011af5  jz      short loc_140011B2F
0x140011af7  mov     [rax+8], r12
0x140011afb  jmp     short loc_140011B2F
0x140011afd  mov     rax, [rsi]
0x140011b00  cmp     rax, rbx
0x140011b03  jnz     short loc_140011B17
0x140011b05  mov     rax, [rax+8]
0x140011b09  mov     [rsi], rax
0x140011b0c  test    rax, rax
0x140011b0f  jz      short loc_140011B2F
0x140011b11  mov     [rax+10h], r12
0x140011b15  jmp     short loc_140011B2F
0x140011b17  mov     rcx, [rbx+10h]
0x140011b1b  mov     rax, [rbx+8]
0x140011b1f  mov     [rcx+8], rax
0x140011b23  mov     rcx, [rbx+8]
0x140011b27  mov     rax, [rbx+10h]
0x140011b2b  mov     [rcx+10h], rax
0x140011b2f  mov     rcx, [rbx]
0x140011b32  test    rcx, rcx
0x140011b35  jz      short loc_140011B43
0x140011b37  mov     rax, [rcx]
0x140011b3a  mov     rax, [rax+10h]
0x140011b3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011b43  mov     edx, 18h
0x140011b48  mov     rcx, rbx; Block
0x140011b4b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140011b50  add     dword ptr [rdi+30h], 0FFFFFFFFh
0x140011b54  jnz     short loc_140011B5D
0x140011b56  mov     [rdi+28h], r12
0x140011b5a  mov     [rsi], r12
0x140011b5d  lea     rcx, [rdi+38h]; lpCriticalSection
0x140011b61  call    cs:__imp_LeaveCriticalSection
0x140011b67  test    r13d, r13d
0x140011b6a  jz      short loc_140011B93
0x140011b6c  mov     rcx, [r15+30h]; this
0x140011b70  call    ?DecUIRefCnt@TLoad64BitDllsMgr@@QEAAXXZ; TLoad64BitDllsMgr::DecUIRefCnt(void)
0x140011b75  jmp     short loc_140011B93
0x140011b77  mov     r14d, 57h ; 'W'
0x140011b7d  lea     rdx, aFailedToProces_0; "Failed to process port closure.  Error "...
0x140011b84  mov     r8d, r14d
0x140011b87  lea     rcx, aTlpcmgrProcess_0; "TLPCMgr::ProcessPortShutdown"
0x140011b8e  call    ?WriteDbgTraceError@SplWow64Telemetry@@SAXPEADPEAGZZ; SplWow64Telemetry::WriteDbgTraceError(char *,ushort *,...)
0x140011b93  mov     eax, r14d
0x140011b96  add     rsp, 38h
0x140011b9a  pop     r15
0x140011b9c  pop     r14
0x140011b9e  pop     r13
0x140011ba0  pop     r12
0x140011ba2  pop     rdi
0x140011ba3  pop     rsi
0x140011ba4  pop     rbp
0x140011ba5  pop     rbx
0x140011ba6  retn
```
