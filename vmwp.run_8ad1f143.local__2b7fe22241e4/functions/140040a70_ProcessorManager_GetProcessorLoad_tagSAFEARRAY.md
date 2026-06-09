# ProcessorManager::GetProcessorLoad(tagSAFEARRAY * *)

- ea: `0x140040a70`
- end: `0x140040df6`
- name: `?GetProcessorLoad@ProcessorManager@@UEAAXPEAPEAUtagSAFEARRAY@@@Z`
- size: `902`
- prototype: `void __fastcall(ProcessorManager *__hidden this, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140023d40`
- `0x140023dc0`
- `0x140023e20`
- `0x140040a70`
- `0x140040ff8`
- `0x140041a5c`
- `0x14006af58`
- `0x14009d7cc`
- `0x1400e4e94`
- `0x140132cd0`
- `0x14013361c`
- `0x140135955`
- `0x140135961`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140040d6e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140040d6e`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x140040c94`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x140040c94`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140040cc9`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140040cc9`
- `OLEAUT32!__imp_SafeArrayCreateVectorEx` at `0x140040c65`
- `OLEAUT32!__imp_SafeArrayCreateVectorEx` at `0x140040c65`

## string_xrefs

- `0x140040d98`: `onecore\vm\common\vml\VmReaderWriterLock.h`
- `0x140040db4`: `onecore\vm\common\vml\VmAutomation.h`
- `0x140040dc9`: `onecore\vm\common\vml\VmAutomation.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ProcessorManager::GetProcessorLoad(ProcessorManager *this, struct tagSAFEARRAY **a2)
{
  __int64 v3; // rsi
  __int64 v4; // rdi
  __int64 size_of; // rax
  void *v6; // rbx
  signed __int32 *v7; // rdi
  signed __int32 v8; // eax
  signed __int32 v9; // ebx
  __int64 v10; // r11
  __int64 v11; // rbx
  unsigned __int64 v12; // r8
  __int64 i; // r9
  __int64 v14; // rax
  __int64 v15; // rcx
  double v16; // xmm0_8
  double v17; // xmm0_8
  double v18; // xmm0_8
  double v19; // xmm1_8
  signed __int64 v20; // rbx
  SAFEARRAY *Vector; // rax
  struct tagSAFEARRAY *v22; // rdi
  HRESULT v23; // eax
  void *v24; // rcx
  SAFEARRAY *v25; // rdx
  signed __int32 v26; // edx
  void *v27; // [rsp+20h] [rbp-30h] BYREF
  void *Src[2]; // [rsp+28h] [rbp-28h] BYREF
  __int64 v29; // [rsp+38h] [rbp-18h]
  SAFEARRAY *psa; // [rsp+40h] [rbp-10h] BYREF
  void *ppvData; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]

  *a2 = 0;
  v27 = 0;
  *(_OWORD *)Src = 0;
  v29 = 0;
  v3 = *((_QWORD *)this + 93);
  v4 = *(unsigned int *)(v3 + 80);
  if ( *(_DWORD *)(v3 + 80) )
  {
    size_of = std::_Get_size_of_n<4>((unsigned int)v4);
    v6 = (void *)std::_Allocate<16,std::_Default_allocate_traits>(size_of);
    memset_0(v6, 0, 4 * v4);
    memmove_0(v6, Src[0], (char *)Src[1] - (char *)Src[0]);
    std::vector<unsigned long>::_Change_array(Src, v6, (unsigned int)v4, (unsigned int)v4, v27);
  }
  v7 = (signed __int32 *)(v3 + 112);
  v8 = _InterlockedCompareExchange((volatile signed __int32 *)(v3 + 112), 4, 0);
  v9 = v8;
  if ( v8 )
  {
    if ( (v8 & 1) != 0 && *(_DWORD *)(v3 + 116) == GetCurrentThreadId() )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v3 + 120));
    }
    else
    {
      do
      {
        while ( (v9 & 1) != 0 )
        {
          if ( !(unsigned int)RrwpLockWait(v3 + 112, 0xFFFFFFFFLL, 0) )
            wil::details::in1diag3::Throw_Win32(
              retaddr,
              (void *)0x249,
              (unsigned int)"onecore\\vm\\common\\vml\\VmReaderWriterLock.h",
              (const char *)0x102,
              (unsigned int)v27);
          _m_prefetchw(v7);
          v9 = *v7;
        }
        v26 = v9;
        v9 = _InterlockedCompareExchange(v7, v9 + 4, v9);
      }
      while ( v9 != v26 );
    }
  }
  if ( *(_DWORD *)(v3 + 164) >= 2u )
  {
    v10 = (*(_DWORD *)(v3 + 160) + 100) % 0x65u;
    v11 = ((int)v10 + 100) % 0x65u;
    v12 = *(_QWORD *)(16392 * v10 + v3 + 16552) - *(_QWORD *)(16392 * v11 + v3 + 16552);
    for ( i = 0; (unsigned int)i < *(_DWORD *)(v3 + 80); i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i >= 0x800 )
        break;
      v14 = (unsigned int)i + 2049 * v11;
      v15 = v12;
      if ( v12 >= *(_QWORD *)(v3 + 8 * ((unsigned int)i + 2049 * v10) + 168) - *(_QWORD *)(v3 + 8 * v14 + 168) )
        v15 = *(_QWORD *)(v3 + 8 * ((unsigned int)i + 2049 * v10) + 168) - *(_QWORD *)(v3 + 8 * v14 + 168);
      v16 = 0.0;
      if ( v12 )
      {
        if ( v15 < 0 )
          v17 = (double)(int)(v15 & 1 | ((unsigned __int64)v15 >> 1))
              + (double)(int)(v15 & 1 | ((unsigned __int64)v15 >> 1));
        else
          v17 = (double)(int)v15;
        v18 = v17 * 100000.0;
        if ( (v12 & 0x8000000000000000uLL) != 0LL )
          v19 = (double)(int)(v12 & 1 | (v12 >> 1)) + (double)(int)(v12 & 1 | (v12 >> 1));
        else
          v19 = (double)(int)v12;
        v16 = v18 / v19;
      }
      *((_DWORD *)Src[0] + i) = (int)v16;
    }
  }
  RrwLockRelease(v3 + 112);
  v20 = ((char *)Src[1] - (char *)Src[0]) >> 2;
  Vector = SafeArrayCreateVectorEx(0x13u, 0, v20, 0);
  v22 = Vector;
  if ( !Vector )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x250,
      (unsigned int)"onecore\\vm\\common\\vml\\VmAutomation.h",
      (const char *)0x8007000ELL,
      (int)v27);
  v27 = Vector;
  psa = Vector;
  ppvData = 0;
  v23 = SafeArrayAccessData(Vector, &ppvData);
  if ( v23 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7B2,
      (unsigned int)"onecore\\vm\\common\\vml\\VmAutomation.h",
      (const char *)(unsigned int)v23,
      (int)v27);
  memcpy_0(ppvData, Src[0], 4LL * (unsigned int)v20);
  if ( psa )
    SafeArrayUnaccessData(psa);
  *a2 = v22;
  v24 = Src[0];
  if ( Src[0] )
  {
    v25 = (SAFEARRAY *)((v29 - (unsigned __int64)Src[0]) & 0xFFFFFFFFFFFFFFFCuLL);
    psa = v25;
    v27 = Src[0];
    if ( (unsigned __int64)v25 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v27, (unsigned __int64 *)&psa);
      v25 = psa;
      v24 = v27;
    }
    operator delete(v24, (const struct std::nothrow_t *)v25);
  }
}

```

## disassembly

```asm
0x140040a70  mov     [rsp-18h+arg_10], rbx
0x140040a75  mov     [rsp-18h+arg_18], rsi
0x140040a7a  push    rbp
0x140040a7b  push    rdi
0x140040a7c  push    r14
0x140040a7e  mov     rbp, rsp
0x140040a81  sub     rsp, 50h
0x140040a85  mov     r14, rdx
0x140040a88  mov     qword ptr [rdx], 0
0x140040a8f  mov     [rbp+var_30], 0
0x140040a97  xor     eax, eax
0x140040a99  xorps   xmm1, xmm1
0x140040a9c  movdqu  xmmword ptr [rbp+Src], xmm1
0x140040aa1  mov     [rbp+var_18], rax
0x140040aa5  mov     rsi, [rcx+2E8h]
0x140040aac  mov     edi, [rsi+50h]
0x140040aaf  test    rdi, rdi
0x140040ab2  jz      short loc_140040AFD
0x140040ab4  mov     ecx, edi
0x140040ab6  call    ??$_Get_size_of_n@$03@std@@YA_K_K@Z; std::_Get_size_of_n<4>(unsigned __int64)
0x140040abb  mov     rcx, rax
0x140040abe  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x140040ac3  mov     rbx, rax
0x140040ac6  lea     r8, ds:0[rdi*4]; Size
0x140040ace  xor     edx, edx; Val
0x140040ad0  mov     rcx, rax; void *
0x140040ad3  call    memset_0
0x140040ad8  mov     rdx, [rbp+Src]; Src
0x140040adc  mov     r8, [rbp+Src+8]
0x140040ae0  sub     r8, rdx; Size
0x140040ae3  mov     rcx, rbx; void *
0x140040ae6  call    memmove_0
0x140040aeb  mov     r9d, edi
0x140040aee  mov     r8d, edi
0x140040af1  mov     rdx, rbx
0x140040af4  lea     rcx, [rbp+Src]
0x140040af8  call    ?_Change_array@?$vector@KV?$allocator@K@std@@@std@@AEAAXQEAK_K1@Z; std::vector<ulong>::_Change_array(ulong * const,unsigned __int64,unsigned __int64)
0x140040afd  lea     rdi, [rsi+70h]
0x140040b01  mov     ecx, 4
0x140040b06  xor     eax, eax
0x140040b08  lock cmpxchg [rdi], ecx
0x140040b0c  mov     ebx, eax
0x140040b0e  jz      short loc_140040B3E
0x140040b10  test    al, 1
0x140040b12  jnz     loc_140040D6E
0x140040b18  test    bl, 1
0x140040b1b  jz      loc_140040D1D
0x140040b21  xor     r8d, r8d
0x140040b24  or      edx, 0FFFFFFFFh
0x140040b27  mov     rcx, rdi
0x140040b2a  call    RrwpLockWait
0x140040b2f  test    eax, eax
0x140040b31  jz      loc_140040D8E
0x140040b37  prefetchw byte ptr [rdi]
0x140040b3a  mov     ebx, [rdi]
0x140040b3c  jmp     short loc_140040B18
0x140040b3e  cmp     dword ptr [rsi+0A4h], 2
0x140040b45  jb      loc_140040C44
0x140040b4b  mov     r8d, [rsi+0A0h]
0x140040b52  add     r8d, 64h ; 'd'
0x140040b56  mov     r9d, 446F8657h
0x140040b5c  mov     eax, r9d
0x140040b5f  mul     r8d
0x140040b62  mov     ecx, r8d
0x140040b65  sub     ecx, edx
0x140040b67  shr     ecx, 1
0x140040b69  add     ecx, edx
0x140040b6b  shr     ecx, 6
0x140040b6e  imul    ecx, 65h ; 'e'
0x140040b71  sub     r8d, ecx
0x140040b74  mov     r11d, r8d
0x140040b77  lea     ecx, [r8+64h]
0x140040b7b  mov     eax, r9d
0x140040b7e  mul     ecx
0x140040b80  mov     eax, ecx
0x140040b82  sub     eax, edx
0x140040b84  shr     eax, 1
0x140040b86  add     eax, edx
0x140040b88  shr     eax, 6
0x140040b8b  imul    eax, 65h ; 'e'
0x140040b8e  sub     ecx, eax
0x140040b90  mov     ebx, ecx
0x140040b92  imul    rcx, r11, 4008h
0x140040b99  imul    rax, rbx, 4008h
0x140040ba0  mov     r8, [rcx+rsi+40A8h]
0x140040ba8  sub     r8, [rax+rsi+40A8h]
0x140040bb0  xor     r9d, r9d
0x140040bb3  cmp     [rsi+50h], r9d
0x140040bb7  jbe     loc_140040C44
0x140040bbd  cmp     r9d, 800h
0x140040bc4  jnb     short loc_140040C44
0x140040bc6  mov     r10d, r9d
0x140040bc9  imul    rcx, r11, 801h
0x140040bd0  add     rcx, r10
0x140040bd3  imul    rax, rbx, 801h
0x140040bda  add     rax, r10
0x140040bdd  mov     rdx, [rsi+rcx*8+0A8h]
0x140040be5  sub     rdx, [rsi+rax*8+0A8h]
0x140040bed  mov     rcx, r8
0x140040bf0  cmp     r8, rdx
0x140040bf3  cmovnb  rcx, rdx
0x140040bf7  xorps   xmm0, xmm0
0x140040bfa  test    r8, r8
0x140040bfd  jz      short loc_140040C2A
0x140040bff  test    rcx, rcx
0x140040c02  js      loc_140040D37
0x140040c08  cvtsi2sd xmm0, rcx
0x140040c0d  mulsd   xmm0, cs:__real@40f86a0000000000
0x140040c15  xorps   xmm1, xmm1
0x140040c18  test    r8, r8
0x140040c1b  js      loc_140040D51
0x140040c21  cvtsi2sd xmm1, r8
0x140040c26  divsd   xmm0, xmm1
0x140040c2a  cvttsd2si rdx, xmm0
0x140040c2f  mov     rax, [rbp+Src]
0x140040c33  mov     [rax+r9*4], edx
0x140040c37  inc     r9d
0x140040c3a  cmp     r9d, [rsi+50h]
0x140040c3e  jb      loc_140040BBD
0x140040c44  mov     rcx, rdi
0x140040c47  call    RrwLockRelease
0x140040c4c  mov     rbx, [rbp+Src+8]
0x140040c50  sub     rbx, [rbp+Src]
0x140040c54  sar     rbx, 2
0x140040c58  mov     ecx, 13h; vt
0x140040c5d  xor     r9d, r9d; pvExtra
0x140040c60  mov     r8d, ebx; cElements
0x140040c63  xor     edx, edx; lLbound
0x140040c65  call    cs:__imp_SafeArrayCreateVectorEx
0x140040c6c  nop     dword ptr [rax+rax+00h]
0x140040c71  mov     rdi, rax
0x140040c74  test    rax, rax
0x140040c77  jz      loc_140040DAA
0x140040c7d  mov     [rbp+var_30], rax
0x140040c81  mov     [rbp+psa], rax
0x140040c85  mov     [rbp+ppvData], 0
0x140040c8d  lea     rdx, [rbp+ppvData]; ppvData
0x140040c91  mov     rcx, rax; psa
0x140040c94  call    cs:__imp_SafeArrayAccessData
0x140040c9b  nop     dword ptr [rax+rax+00h]
0x140040ca0  mov     rcx, [rbp+18h]; this
0x140040ca4  test    eax, eax
0x140040ca6  js      loc_140040DC6
0x140040cac  mov     r8d, ebx
0x140040caf  shl     r8, 2; Size
0x140040cb3  mov     rdx, [rbp+Src]; Src
0x140040cb7  mov     rcx, [rbp+ppvData]; void *
0x140040cbb  call    memcpy_0
0x140040cc0  mov     rcx, [rbp+psa]; psa
0x140040cc4  test    rcx, rcx
0x140040cc7  jz      short loc_140040CD5
0x140040cc9  call    cs:__imp_SafeArrayUnaccessData
0x140040cd0  nop     dword ptr [rax+rax+00h]
0x140040cd5  mov     [r14], rdi
0x140040cd8  mov     rcx, [rbp+Src]; void *
0x140040cdc  test    rcx, rcx
0x140040cdf  jz      short loc_140040D07
0x140040ce1  mov     rdx, [rbp+var_18]
0x140040ce5  sub     rdx, rcx
0x140040ce8  and     rdx, 0FFFFFFFFFFFFFFFCh; struct std::nothrow_t *
0x140040cec  mov     [rbp+psa], rdx
0x140040cf0  mov     [rbp+var_30], rcx
0x140040cf4  cmp     rdx, 1000h
0x140040cfb  jnb     loc_140040DDB
0x140040d01  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140040d06  nop
0x140040d07  lea     r11, [rsp+50h+var_s0]
0x140040d0c  mov     rbx, [r11+30h]
0x140040d10  mov     rsi, [r11+38h]
0x140040d14  mov     rsp, r11
0x140040d17  pop     r14
0x140040d19  pop     rdi
0x140040d1a  pop     rbp
0x140040d1b  retn
0x140040d1d  mov     edx, ebx
0x140040d1f  lea     ecx, [rbx+4]
0x140040d22  mov     eax, ebx
0x140040d24  lock cmpxchg [rdi], ecx
0x140040d28  mov     ebx, eax
0x140040d2a  cmp     eax, edx
0x140040d2c  jnz     loc_140040B18
0x140040d32  jmp     loc_140040B3E
0x140040d37  mov     rax, rcx
0x140040d3a  shr     rax, 1
0x140040d3d  and     ecx, 1
0x140040d40  or      rax, rcx
0x140040d43  cvtsi2sd xmm0, rax
0x140040d48  addsd   xmm0, xmm0
0x140040d4c  jmp     loc_140040C0D
0x140040d51  mov     rcx, r8
0x140040d54  shr     rcx, 1
0x140040d57  mov     rax, r8
0x140040d5a  and     eax, 1
0x140040d5d  or      rcx, rax
0x140040d60  cvtsi2sd xmm1, rcx
0x140040d65  addsd   xmm1, xmm1
0x140040d69  jmp     loc_140040C26
0x140040d6e  call    cs:__imp_GetCurrentThreadId
0x140040d75  nop     dword ptr [rax+rax+00h]
0x140040d7a  mov     ecx, [rdi+4]
0x140040d7d  cmp     ecx, eax
0x140040d7f  jnz     loc_140040B18
0x140040d85  lock inc dword ptr [rdi+8]
0x140040d89  jmp     loc_140040B3E
0x140040d8e  mov     rcx, [rbp+18h]; this
0x140040d92  mov     r9d, 102h; char *
0x140040d98  lea     r8, aOnecoreVmCommo_24; "onecore\\vm\\common\\vml\\VmReaderWrite"...
0x140040d9f  mov     edx, 249h; void *
0x140040da4  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140040daa  mov     rcx, [rbp+18h]; this
0x140040dae  mov     r9d, 8007000Eh; char *
0x140040db4  lea     r8, aOnecoreVmCommo_54; "onecore\\vm\\common\\vml\\VmAutomation."...
0x140040dbb  mov     edx, 250h; void *
0x140040dc0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140040dc6  mov     r9d, eax; char *
0x140040dc9  lea     r8, aOnecoreVmCommo_54; "onecore\\vm\\common\\vml\\VmAutomation."...
0x140040dd0  mov     edx, 7B2h; void *
0x140040dd5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140040ddb  lea     rdx, [rbp+psa]; unsigned __int64 *
0x140040ddf  lea     rcx, [rbp+var_30]; void **
0x140040de3  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x140040de8  mov     rdx, [rbp+psa]
0x140040dec  mov     rcx, [rbp+var_30]
0x140040df0  jmp     loc_140040D01
```
