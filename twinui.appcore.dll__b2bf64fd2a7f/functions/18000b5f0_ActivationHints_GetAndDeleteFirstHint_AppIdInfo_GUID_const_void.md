# ActivationHints::GetAndDeleteFirstHint(AppIdInfo,_GUID const &,void * *)

- ea: `0x18000b5f0`
- end: `0x18000b97a`
- name: `?GetAndDeleteFirstHint@ActivationHints@@UEAAJUAppIdInfo@@AEBU_GUID@@PEAPEAX@Z`
- size: `906`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18000b5f0`
- `0x18000b9e8`
- `0x180017248`
- `0x18001cc38`
- `0x1800222b0`
- `0x1800336f8`
- `0x180033d5c`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b62c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b62c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b7fe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b7fe`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000b70f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000b743`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000b70f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000b743`
- `msvcp_win!_Query_perf_frequency` at `0x18000b637`
- `msvcp_win!_Query_perf_frequency` at `0x18000b637`
- `msvcp_win!_Query_perf_counter` at `0x18000b640`
- `msvcp_win!_Query_perf_counter` at `0x18000b640`

## string_xrefs

- `0x18000b949`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
__int64 __fastcall ActivationHints::GetAndDeleteFirstHint(RTL_SRWLOCK *a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  RTL_SRWLOCK *v6; // rbx
  __int64 perf_frequency; // rdi
  __int64 perf_counter; // rax
  __int64 v9; // r8
  __int64 Ptr; // rdx
  const char *v11; // r9
  const char *v12; // rcx
  const WCHAR *v13; // r12
  __int64 v14; // r13
  __int64 v15; // r15
  int v16; // eax
  const WCHAR *v17; // rcx
  __int64 v18; // rdi
  PVOID i; // rsi
  const WCHAR *v20; // rcx
  int v21; // eax
  __int64 v22; // rsi
  PVOID v23; // r15
  __int64 j; // r14
  int v25; // eax
  __int64 result; // rax
  const WCHAR *v27; // rcx
  ActivationHints::Hint *v28; // rdi
  BOOL bIgnoreCase; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  const WCHAR *lpString2; // [rsp+88h] [rbp+10h]

  try
  {
    *a4 = 0;
    if ( *(_QWORD *)a2 || *(_QWORD *)(a2 + 8) )
    {
      v6 = a1 + 7;
      AcquireSRWLockExclusive(a1 + 7);
      perf_frequency = _Query_perf_frequency();
      perf_counter = _Query_perf_counter();
      if ( perf_frequency == 10000000 )
      {
        v9 = 100 * perf_counter;
      }
      else if ( perf_frequency == 24000000 )
      {
        v9 = 1000000000 * (perf_counter % 24000000) / 24000000 + 1000000000 * (perf_counter / 24000000);
      }
      else
      {
        v9 = 1000000000 * (perf_counter % perf_frequency) / perf_frequency
           + 1000000000 * (perf_counter / perf_frequency);
      }
      Ptr = (__int64)a1[9].Ptr;
      v11 = (const char *)a1[8].Ptr;
      v12 = v11;
      if ( v11 != (const char *)Ptr )
      {
        do
        {
          if ( v9 - *((_QWORD *)v12 + 9) <= 120000000000LL )
            break;
          v12 += 88;
        }
        while ( v12 != (const char *)Ptr );
        if ( v11 != v12 )
        {
          v28 = (ActivationHints::Hint *)std::_Move_unchecked<ActivationHints::Hint *,ActivationHints::Hint *>(
                                           v12,
                                           Ptr,
                                           a1[8].Ptr);
          std::_Destroy_range<std::allocator<ActivationHints::Hint>>(v28);
          a1[9].Ptr = v28;
        }
      }
      v13 = *(const WCHAR **)a2;
      v14 = -1;
      if ( *(_QWORD *)a2 )
      {
        v15 = -1;
        do
          ++v15;
        while ( v13[v15] );
        v16 = v15;
      }
      else
      {
        LODWORD(v15) = 0;
        v16 = 0;
      }
      v17 = *(const WCHAR **)(a2 + 8);
      lpString2 = v17;
      if ( v17 )
      {
        do
          ++v14;
        while ( v17[v14] );
      }
      else
      {
        lpString2 = 0;
        LODWORD(v14) = 0;
        LODWORD(v15) = v16;
      }
      v18 = (__int64)a1[8].Ptr;
      for ( i = a1[9].Ptr; (PVOID)v18 != i; v18 += 88 )
      {
        if ( *(_QWORD *)(v18 + 24) <= 7u )
          v20 = (const WCHAR *)v18;
        else
          v20 = *(const WCHAR **)v18;
        if ( CompareStringOrdinal(v20, *(_DWORD *)(v18 + 16), v13, v15, 1) == 2 )
          goto LABEL_21;
        v27 = (const WCHAR *)(v18 + 32);
        if ( *(_QWORD *)(v18 + 56) > 7u )
          v27 = *(const WCHAR **)v27;
        if ( CompareStringOrdinal(v27, *(_DWORD *)(v18 + 48), lpString2, v14, 1) == 2 )
        {
LABEL_21:
          v21 = *(_DWORD *)(a2 + 16);
          if ( !v21 || *(_DWORD *)(v18 + 64) == v21 )
            break;
        }
      }
      if ( (PVOID)v18 != a1[9].Ptr )
      {
        v22 = *(_QWORD *)(v18 + 80);
        if ( v22 )
          (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v22 + 8LL))(v22, Ptr, v9);
        v23 = a1[9].Ptr;
        for ( j = v18 + 88; (PVOID)j != v23; j += 88 )
        {
          ActivationHints::Hint::operator=(v18, j);
          v18 += 88;
        }
        ActivationHints::Hint::~Hint((ActivationHints::Hint *)((char *)a1[9].Ptr - 88), Ptr, v9, (__int64)v11);
        a1[9].Ptr = (char *)a1[9].Ptr - 88;
        if ( v22 )
        {
          v25 = (**(__int64 (__fastcall ***)(__int64, __int64, _QWORD *))v22)(v22, a3, a4);
          if ( v25 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1CBE,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
              (const char *)(unsigned int)v25,
              bIgnoreCase);
        }
        else
        {
          *a4 = 0;
        }
        if ( v22 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      }
      if ( v6 )
        ReleaseSRWLockExclusive(v6);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB3,
        (unsigned int)"onecoreuap\\shell\\twinui\\activation\\lib\\activationhints.cpp",
        (const char *)0x80070057LL,
        bIgnoreCase);
      result = 2147942487LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xD6,
                           (unsigned int)"onecoreuap\\shell\\twinui\\activation\\lib\\activationhints.cpp",
                           v11);
  }
  return result;
}

```

## disassembly

```asm
0x18000b5f0  mov     [rsp+arg_18], r9
0x18000b5f5  mov     [rsp+arg_10], r8
0x18000b5fa  mov     [rsp+arg_0], rcx
0x18000b5ff  push    rbx
0x18000b600  push    rsi
0x18000b601  push    rdi
0x18000b602  push    r12
0x18000b604  push    r13
0x18000b606  push    r14
0x18000b608  push    r15
0x18000b60a  sub     rsp, 40h
0x18000b60e  mov     r14, rdx
0x18000b611  mov     rsi, rcx
0x18000b614  mov     qword ptr [r9], 0
0x18000b61b  cmp     qword ptr [rdx], 0
0x18000b61f  jz      loc_18000B856
0x18000b625  lea     rbx, [rcx+38h]
0x18000b629  mov     rcx, rbx; SRWLock
0x18000b62c  call    cs:__imp_AcquireSRWLockExclusive
0x18000b632  mov     [rsp+78h+var_48], rbx
0x18000b637  call    cs:__imp__Query_perf_frequency
0x18000b63d  mov     rdi, rax
0x18000b640  call    cs:__imp__Query_perf_counter
0x18000b646  mov     r9, rax
0x18000b649  cmp     rdi, 989680h
0x18000b650  jnz     loc_18000B884
0x18000b656  imul    r8, r9, 64h ; 'd'
0x18000b65a  mov     rdx, [rsi+48h]
0x18000b65e  mov     r9, [rsi+40h]
0x18000b662  mov     rcx, r9
0x18000b665  cmp     r9, rdx
0x18000b668  jz      short loc_18000B692
0x18000b66a  mov     r10, 1BF08EB000h
0x18000b674  mov     rax, r8
0x18000b677  sub     rax, [rcx+48h]
0x18000b67b  cmp     r10, rax
0x18000b67e  jge     short loc_18000B689
0x18000b680  add     rcx, 58h ; 'X'
0x18000b684  cmp     rcx, rdx
0x18000b687  jnz     short loc_18000B674
0x18000b689  cmp     r9, rcx
0x18000b68c  jnz     loc_18000B909
0x18000b692  mov     r12, [r14]
0x18000b695  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18000b69c  test    r12, r12
0x18000b69f  jz      loc_18000B835
0x18000b6a5  mov     r15, r13
0x18000b6a8  nop     dword ptr [rax+rax+00000000h]
0x18000b6b0  inc     r15
0x18000b6b3  cmp     word ptr [r12+r15*2], 0
0x18000b6b9  jnz     short loc_18000B6B0
0x18000b6bb  mov     eax, r15d
0x18000b6be  mov     rcx, [r14+8]
0x18000b6c2  mov     [rsp+78h+lpString2], rcx
0x18000b6ca  test    rcx, rcx
0x18000b6cd  jz      loc_18000B83F
0x18000b6d3  inc     r13
0x18000b6d6  cmp     word ptr [rcx+r13*2], 0
0x18000b6dc  jnz     short loc_18000B6D3
0x18000b6de  mov     rdi, [rsi+40h]
0x18000b6e2  mov     rsi, [rsi+48h]
0x18000b6e6  cmp     rdi, rsi
0x18000b6e9  jz      short loc_18000B757
0x18000b6eb  nop     dword ptr [rax+rax+00h]
0x18000b6f0  cmp     qword ptr [rdi+18h], 7
0x18000b6f5  jbe     loc_18000B816
0x18000b6fb  mov     rcx, [rdi]; lpString1
0x18000b6fe  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x18000b706  mov     r9d, r15d; cchCount2
0x18000b709  mov     r8, r12; lpString2
0x18000b70c  mov     edx, [rdi+10h]; cchCount1
0x18000b70f  call    cs:__imp_CompareStringOrdinal
0x18000b715  cmp     eax, 2
0x18000b718  jnz     loc_18000B81E
0x18000b71e  mov     eax, [r14+10h]
0x18000b722  test    eax, eax
0x18000b724  jz      short loc_18000B757
0x18000b726  cmp     [rdi+40h], eax
0x18000b729  jz      short loc_18000B757
0x18000b72b  jmp     short loc_18000B74E
0x18000b72d  mov     [rsp+78h+bIgnoreCase], 1; int
0x18000b735  mov     r9d, r13d; cchCount2
0x18000b738  mov     r8, [rsp+78h+lpString2]; lpString2
0x18000b740  mov     edx, [rdi+30h]; cchCount1
0x18000b743  call    cs:__imp_CompareStringOrdinal
0x18000b749  cmp     eax, 2
0x18000b74c  jz      short loc_18000B71E
0x18000b74e  add     rdi, 58h ; 'X'
0x18000b752  cmp     rdi, rsi
0x18000b755  jnz     short loc_18000B6F0
0x18000b757  mov     r13, [rsp+78h+arg_0]
0x18000b75f  cmp     rdi, [r13+48h]
0x18000b763  jz      loc_18000B7F6
0x18000b769  mov     rsi, [rdi+50h]
0x18000b76d  mov     [rsp+78h+lpString2], rsi
0x18000b775  test    rsi, rsi
0x18000b778  jz      short loc_18000B78A
0x18000b77a  mov     rax, [rsi]
0x18000b77d  mov     rcx, rsi
0x18000b780  mov     rax, [rax+8]
0x18000b784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b789  nop
0x18000b78a  mov     r15, [r13+48h]
0x18000b78e  lea     r14, [rdi+58h]
0x18000b792  cmp     r14, r15
0x18000b795  jnz     loc_18000B929
0x18000b79b  mov     rcx, [r13+48h]
0x18000b79f  sub     rcx, 58h ; 'X'; this
0x18000b7a3  call    ??1Hint@ActivationHints@@QEAA@XZ; ActivationHints::Hint::~Hint(void)
0x18000b7a8  add     qword ptr [r13+48h], 0FFFFFFFFFFFFFFA8h
0x18000b7ad  test    rsi, rsi
0x18000b7b0  jz      loc_18000B95A
0x18000b7b6  mov     rax, [rsi]
0x18000b7b9  mov     r8, [rsp+78h+arg_18]
0x18000b7c1  mov     rdx, [rsp+78h+arg_10]
0x18000b7c9  mov     rcx, rsi
0x18000b7cc  mov     rax, [rax]
0x18000b7cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7d4  mov     rcx, [rsp+78h]; this
0x18000b7d9  test    eax, eax
0x18000b7db  js      loc_18000B946
0x18000b7e1  test    rsi, rsi
0x18000b7e4  jz      short loc_18000B7F6
0x18000b7e6  mov     rax, [rsi]
0x18000b7e9  mov     rcx, rsi
0x18000b7ec  mov     rax, [rax+10h]
0x18000b7f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7f5  nop
0x18000b7f6  test    rbx, rbx
0x18000b7f9  jz      short loc_18000B804
0x18000b7fb  mov     rcx, rbx; SRWLock
0x18000b7fe  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b804  xor     eax, eax
0x18000b806  add     rsp, 40h
0x18000b80a  pop     r15
0x18000b80c  pop     r14
0x18000b80e  pop     r13
0x18000b810  pop     r12
0x18000b812  pop     rdi
0x18000b813  pop     rsi
0x18000b814  pop     rbx
0x18000b815  retn
0x18000b816  mov     rcx, rdi
0x18000b819  jmp     loc_18000B6FE
0x18000b81e  lea     rcx, [rdi+20h]; lpString1
0x18000b822  cmp     qword ptr [rdi+38h], 7
0x18000b827  jbe     loc_18000B72D
0x18000b82d  mov     rcx, [rcx]
0x18000b830  jmp     loc_18000B72D
0x18000b835  xor     r15d, r15d
0x18000b838  xor     eax, eax
0x18000b83a  jmp     loc_18000B6BE
0x18000b83f  mov     [rsp+78h+lpString2], 0
0x18000b84b  xor     r13d, r13d
0x18000b84e  mov     r15d, eax
0x18000b851  jmp     loc_18000B6DE
0x18000b856  cmp     qword ptr [rdx+8], 0
0x18000b85b  jnz     loc_18000B625
0x18000b861  mov     rcx, [rsp+78h]; this
0x18000b866  mov     r9d, 80070057h; char *
0x18000b86c  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\twinui\\activation\\"...
0x18000b873  mov     edx, 0B3h; void *
0x18000b878  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b87d  mov     eax, 80070057h
0x18000b882  jmp     short loc_18000B806
0x18000b884  cmp     rdi, 16E3600h
0x18000b88b  jnz     short loc_18000B8E6
0x18000b88d  mov     r10, 0B2F4FC0794908CF3h
0x18000b897  mov     rax, r10
0x18000b89a  imul    r9
0x18000b89d  lea     r8, [r9+rdx]
0x18000b8a1  sar     r8, 18h
0x18000b8a5  mov     rcx, r8
0x18000b8a8  shr     rcx, 3Fh
0x18000b8ac  add     r8, rcx
0x18000b8af  imul    rcx, r8, 16E3600h
0x18000b8b6  sub     r9, rcx
0x18000b8b9  imul    rcx, r9, 3B9ACA00h
0x18000b8c0  mov     rax, r10
0x18000b8c3  imul    rcx
0x18000b8c6  add     rdx, rcx
0x18000b8c9  sar     rdx, 18h
0x18000b8cd  mov     rax, rdx
0x18000b8d0  shr     rax, 3Fh
0x18000b8d4  add     rdx, rax
0x18000b8d7  imul    r8, 3B9ACA00h
0x18000b8de  add     r8, rdx
0x18000b8e1  jmp     loc_18000B65A
0x18000b8e6  cqo
0x18000b8e8  idiv    rdi
0x18000b8eb  mov     rcx, rax
0x18000b8ee  imul    rax, rdx, 3B9ACA00h
0x18000b8f5  cqo
0x18000b8f7  idiv    rdi
0x18000b8fa  imul    r8, rcx, 3B9ACA00h
0x18000b901  add     r8, rax
0x18000b904  jmp     loc_18000B65A
0x18000b909  mov     r8, r9
0x18000b90c  call    ??$_Move_unchecked@PEAUHint@ActivationHints@@PEAU12@@std@@YAPEAUHint@ActivationHints@@PEAU12@00@Z; std::_Move_unchecked<ActivationHints::Hint *,ActivationHints::Hint *>(ActivationHints::Hint *,ActivationHints::Hint *,ActivationHints::Hint *)
0x18000b911  mov     rdi, rax
0x18000b914  mov     rdx, [rsi+48h]
0x18000b918  mov     rcx, rax; this
0x18000b91b  call    ??$_Destroy_range@V?$allocator@UHint@ActivationHints@@@std@@@std@@YAXPEAUHint@ActivationHints@@QEAU12@AEAV?$allocator@UHint@ActivationHints@@@0@@Z; std::_Destroy_range<std::allocator<ActivationHints::Hint>>(ActivationHints::Hint *,ActivationHints::Hint * const,std::allocator<ActivationHints::Hint> &)
0x18000b920  mov     [rsi+48h], rdi
0x18000b924  jmp     loc_18000B692
0x18000b929  mov     rdx, r14
0x18000b92c  mov     rcx, rdi
0x18000b92f  call    ??4Hint@ActivationHints@@QEAAAEAU01@$$QEAU01@@Z; ActivationHints::Hint::operator=(ActivationHints::Hint &&)
0x18000b934  add     rdi, 58h ; 'X'
0x18000b938  add     r14, 58h ; 'X'
0x18000b93c  cmp     r14, r15
0x18000b93f  jnz     short loc_18000B929
0x18000b941  jmp     loc_18000B79B
0x18000b946  mov     r9d, eax; char *
0x18000b949  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000b950  mov     edx, 1CBEh; void *
0x18000b955  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000b95a  mov     rcx, [rsp+78h+arg_18]
0x18000b962  mov     qword ptr [rcx], 0
0x18000b969  jmp     loc_18000B7E1
0x18000b96e  mov     eax, dword ptr [rsp+78h+arg_18]
0x18000b975  jmp     loc_18000B806
```
