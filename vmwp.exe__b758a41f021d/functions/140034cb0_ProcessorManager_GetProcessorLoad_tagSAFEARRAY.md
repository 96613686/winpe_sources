# ProcessorManager::GetProcessorLoad(tagSAFEARRAY * *)

- ea: `0x140034cb0`
- end: `0x140035036`
- name: `?GetProcessorLoad@ProcessorManager@@UEAAXPEAPEAUtagSAFEARRAY@@@Z`
- size: `902`
- prototype: `void __fastcall(ProcessorManager *__hidden this, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400242b0`
- `0x140024330`
- `0x140024390`
- `0x140034cb0`
- `0x140035238`
- `0x140035c9c`
- `0x140078628`
- `0x1400ba144`
- `0x1400d6174`
- `0x14011edb0`
- `0x14011f6fc`
- `0x140121a35`
- `0x140121a41`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140034fae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140034fae`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x140034ed4`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x140034ed4`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140034f09`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140034f09`
- `OLEAUT32!__imp_SafeArrayCreateVectorEx` at `0x140034ea5`
- `OLEAUT32!__imp_SafeArrayCreateVectorEx` at `0x140034ea5`

## string_xrefs

- `0x140034fd8`: `onecore\vm\common\vml\VmReaderWriterLock.h`
- `0x140034ff4`: `onecore\vm\common\vml\VmAutomation.h`
- `0x140035009`: `onecore\vm\common\vml\VmAutomation.h`

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
0x140034cb0  mov     [rsp-18h+arg_10], rbx
0x140034cb5  mov     [rsp-18h+arg_18], rsi
0x140034cba  push    rbp
0x140034cbb  push    rdi
0x140034cbc  push    r14
0x140034cbe  mov     rbp, rsp
0x140034cc1  sub     rsp, 50h
0x140034cc5  mov     r14, rdx
0x140034cc8  mov     qword ptr [rdx], 0
0x140034ccf  mov     [rbp+var_30], 0
0x140034cd7  xor     eax, eax
0x140034cd9  xorps   xmm1, xmm1
0x140034cdc  movdqu  xmmword ptr [rbp+Src], xmm1
0x140034ce1  mov     [rbp+var_18], rax
0x140034ce5  mov     rsi, [rcx+2E8h]
0x140034cec  mov     edi, [rsi+50h]
0x140034cef  test    rdi, rdi
0x140034cf2  jz      short loc_140034D3D
0x140034cf4  mov     ecx, edi
0x140034cf6  call    ??$_Get_size_of_n@$03@std@@YA_K_K@Z; std::_Get_size_of_n<4>(unsigned __int64)
0x140034cfb  mov     rcx, rax
0x140034cfe  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x140034d03  mov     rbx, rax
0x140034d06  lea     r8, ds:0[rdi*4]; Size
0x140034d0e  xor     edx, edx; Val
0x140034d10  mov     rcx, rax; void *
0x140034d13  call    memset_0
0x140034d18  mov     rdx, [rbp+Src]; Src
0x140034d1c  mov     r8, [rbp+Src+8]
0x140034d20  sub     r8, rdx; Size
0x140034d23  mov     rcx, rbx; void *
0x140034d26  call    memmove_0
0x140034d2b  mov     r9d, edi
0x140034d2e  mov     r8d, edi
0x140034d31  mov     rdx, rbx
0x140034d34  lea     rcx, [rbp+Src]
0x140034d38  call    ?_Change_array@?$vector@KV?$allocator@K@std@@@std@@AEAAXQEAK_K1@Z; std::vector<ulong>::_Change_array(ulong * const,unsigned __int64,unsigned __int64)
0x140034d3d  lea     rdi, [rsi+70h]
0x140034d41  mov     ecx, 4
0x140034d46  xor     eax, eax
0x140034d48  lock cmpxchg [rdi], ecx
0x140034d4c  mov     ebx, eax
0x140034d4e  jz      short loc_140034D7E
0x140034d50  test    al, 1
0x140034d52  jnz     loc_140034FAE
0x140034d58  test    bl, 1
0x140034d5b  jz      loc_140034F5D
0x140034d61  xor     r8d, r8d
0x140034d64  or      edx, 0FFFFFFFFh
0x140034d67  mov     rcx, rdi
0x140034d6a  call    RrwpLockWait
0x140034d6f  test    eax, eax
0x140034d71  jz      loc_140034FCE
0x140034d77  prefetchw byte ptr [rdi]
0x140034d7a  mov     ebx, [rdi]
0x140034d7c  jmp     short loc_140034D58
0x140034d7e  cmp     dword ptr [rsi+0A4h], 2
0x140034d85  jb      loc_140034E84
0x140034d8b  mov     r8d, [rsi+0A0h]
0x140034d92  add     r8d, 64h ; 'd'
0x140034d96  mov     r9d, 446F8657h
0x140034d9c  mov     eax, r9d
0x140034d9f  mul     r8d
0x140034da2  mov     ecx, r8d
0x140034da5  sub     ecx, edx
0x140034da7  shr     ecx, 1
0x140034da9  add     ecx, edx
0x140034dab  shr     ecx, 6
0x140034dae  imul    ecx, 65h ; 'e'
0x140034db1  sub     r8d, ecx
0x140034db4  mov     r11d, r8d
0x140034db7  lea     ecx, [r8+64h]
0x140034dbb  mov     eax, r9d
0x140034dbe  mul     ecx
0x140034dc0  mov     eax, ecx
0x140034dc2  sub     eax, edx
0x140034dc4  shr     eax, 1
0x140034dc6  add     eax, edx
0x140034dc8  shr     eax, 6
0x140034dcb  imul    eax, 65h ; 'e'
0x140034dce  sub     ecx, eax
0x140034dd0  mov     ebx, ecx
0x140034dd2  imul    rcx, r11, 4008h
0x140034dd9  imul    rax, rbx, 4008h
0x140034de0  mov     r8, [rcx+rsi+40A8h]
0x140034de8  sub     r8, [rax+rsi+40A8h]
0x140034df0  xor     r9d, r9d
0x140034df3  cmp     [rsi+50h], r9d
0x140034df7  jbe     loc_140034E84
0x140034dfd  cmp     r9d, 800h
0x140034e04  jnb     short loc_140034E84
0x140034e06  mov     r10d, r9d
0x140034e09  imul    rcx, r11, 801h
0x140034e10  add     rcx, r10
0x140034e13  imul    rax, rbx, 801h
0x140034e1a  add     rax, r10
0x140034e1d  mov     rdx, [rsi+rcx*8+0A8h]
0x140034e25  sub     rdx, [rsi+rax*8+0A8h]
0x140034e2d  mov     rcx, r8
0x140034e30  cmp     r8, rdx
0x140034e33  cmovnb  rcx, rdx
0x140034e37  xorps   xmm0, xmm0
0x140034e3a  test    r8, r8
0x140034e3d  jz      short loc_140034E6A
0x140034e3f  test    rcx, rcx
0x140034e42  js      loc_140034F77
0x140034e48  cvtsi2sd xmm0, rcx
0x140034e4d  mulsd   xmm0, cs:__real@40f86a0000000000
0x140034e55  xorps   xmm1, xmm1
0x140034e58  test    r8, r8
0x140034e5b  js      loc_140034F91
0x140034e61  cvtsi2sd xmm1, r8
0x140034e66  divsd   xmm0, xmm1
0x140034e6a  cvttsd2si rdx, xmm0
0x140034e6f  mov     rax, [rbp+Src]
0x140034e73  mov     [rax+r9*4], edx
0x140034e77  inc     r9d
0x140034e7a  cmp     r9d, [rsi+50h]
0x140034e7e  jb      loc_140034DFD
0x140034e84  mov     rcx, rdi
0x140034e87  call    RrwLockRelease
0x140034e8c  mov     rbx, [rbp+Src+8]
0x140034e90  sub     rbx, [rbp+Src]
0x140034e94  sar     rbx, 2
0x140034e98  mov     ecx, 13h; vt
0x140034e9d  xor     r9d, r9d; pvExtra
0x140034ea0  mov     r8d, ebx; cElements
0x140034ea3  xor     edx, edx; lLbound
0x140034ea5  call    cs:__imp_SafeArrayCreateVectorEx
0x140034eac  nop     dword ptr [rax+rax+00h]
0x140034eb1  mov     rdi, rax
0x140034eb4  test    rax, rax
0x140034eb7  jz      loc_140034FEA
0x140034ebd  mov     [rbp+var_30], rax
0x140034ec1  mov     [rbp+psa], rax
0x140034ec5  mov     [rbp+ppvData], 0
0x140034ecd  lea     rdx, [rbp+ppvData]; ppvData
0x140034ed1  mov     rcx, rax; psa
0x140034ed4  call    cs:__imp_SafeArrayAccessData
0x140034edb  nop     dword ptr [rax+rax+00h]
0x140034ee0  mov     rcx, [rbp+18h]; this
0x140034ee4  test    eax, eax
0x140034ee6  js      loc_140035006
0x140034eec  mov     r8d, ebx
0x140034eef  shl     r8, 2; Size
0x140034ef3  mov     rdx, [rbp+Src]; Src
0x140034ef7  mov     rcx, [rbp+ppvData]; void *
0x140034efb  call    memcpy_0
0x140034f00  mov     rcx, [rbp+psa]; psa
0x140034f04  test    rcx, rcx
0x140034f07  jz      short loc_140034F15
0x140034f09  call    cs:__imp_SafeArrayUnaccessData
0x140034f10  nop     dword ptr [rax+rax+00h]
0x140034f15  mov     [r14], rdi
0x140034f18  mov     rcx, [rbp+Src]; void *
0x140034f1c  test    rcx, rcx
0x140034f1f  jz      short loc_140034F47
0x140034f21  mov     rdx, [rbp+var_18]
0x140034f25  sub     rdx, rcx
0x140034f28  and     rdx, 0FFFFFFFFFFFFFFFCh; struct std::nothrow_t *
0x140034f2c  mov     [rbp+psa], rdx
0x140034f30  mov     [rbp+var_30], rcx
0x140034f34  cmp     rdx, 1000h
0x140034f3b  jnb     loc_14003501B
0x140034f41  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140034f46  nop
0x140034f47  lea     r11, [rsp+50h+var_s0]
0x140034f4c  mov     rbx, [r11+30h]
0x140034f50  mov     rsi, [r11+38h]
0x140034f54  mov     rsp, r11
0x140034f57  pop     r14
0x140034f59  pop     rdi
0x140034f5a  pop     rbp
0x140034f5b  retn
0x140034f5d  mov     edx, ebx
0x140034f5f  lea     ecx, [rbx+4]
0x140034f62  mov     eax, ebx
0x140034f64  lock cmpxchg [rdi], ecx
0x140034f68  mov     ebx, eax
0x140034f6a  cmp     eax, edx
0x140034f6c  jnz     loc_140034D58
0x140034f72  jmp     loc_140034D7E
0x140034f77  mov     rax, rcx
0x140034f7a  shr     rax, 1
0x140034f7d  and     ecx, 1
0x140034f80  or      rax, rcx
0x140034f83  cvtsi2sd xmm0, rax
0x140034f88  addsd   xmm0, xmm0
0x140034f8c  jmp     loc_140034E4D
0x140034f91  mov     rcx, r8
0x140034f94  shr     rcx, 1
0x140034f97  mov     rax, r8
0x140034f9a  and     eax, 1
0x140034f9d  or      rcx, rax
0x140034fa0  cvtsi2sd xmm1, rcx
0x140034fa5  addsd   xmm1, xmm1
0x140034fa9  jmp     loc_140034E66
0x140034fae  call    cs:__imp_GetCurrentThreadId
0x140034fb5  nop     dword ptr [rax+rax+00h]
0x140034fba  mov     ecx, [rdi+4]
0x140034fbd  cmp     ecx, eax
0x140034fbf  jnz     loc_140034D58
0x140034fc5  lock inc dword ptr [rdi+8]
0x140034fc9  jmp     loc_140034D7E
0x140034fce  mov     rcx, [rbp+18h]; this
0x140034fd2  mov     r9d, 102h; char *
0x140034fd8  lea     r8, aOnecoreVmCommo_23; "onecore\\vm\\common\\vml\\VmReaderWrite"...
0x140034fdf  mov     edx, 249h; void *
0x140034fe4  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140034fea  mov     rcx, [rbp+18h]; this
0x140034fee  mov     r9d, 8007000Eh; char *
0x140034ff4  lea     r8, aOnecoreVmCommo_53; "onecore\\vm\\common\\vml\\VmAutomation."...
0x140034ffb  mov     edx, 250h; void *
0x140035000  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140035006  mov     r9d, eax; char *
0x140035009  lea     r8, aOnecoreVmCommo_53; "onecore\\vm\\common\\vml\\VmAutomation."...
0x140035010  mov     edx, 7B2h; void *
0x140035015  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14003501b  lea     rdx, [rbp+psa]; unsigned __int64 *
0x14003501f  lea     rcx, [rbp+var_30]; void **
0x140035023  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x140035028  mov     rdx, [rbp+psa]
0x14003502c  mov     rcx, [rbp+var_30]
0x140035030  jmp     loc_140034F41
```
