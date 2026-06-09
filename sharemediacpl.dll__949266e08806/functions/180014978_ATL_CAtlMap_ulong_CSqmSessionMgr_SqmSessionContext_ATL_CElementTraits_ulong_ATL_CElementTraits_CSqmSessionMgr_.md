# ATL::CAtlMap<ulong,CSqmSessionMgr::SqmSessionContext *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CSqmSessionMgr::SqmSessionContext *>>::PickSize(unsigned __int64)

- ea: `0x180014978`
- end: `0x180014a0d`
- name: `?PickSize@?$CAtlMap@KPEAVSqmSessionContext@CSqmSessionMgr@@V?$CElementTraits@K@ATL@@V?$CElementTraits@PEAVSqmSessionContext@CSqmSessionMgr@@@4@@ATL@@AEBAI_K@Z`
- size: `149`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800146e8`
- `0x180014878`
- `0x180014a14`
- `0x180014aec`
- `0x1800159f8`

## callees

- `0x180014978`

## pseudocode

```c
unsigned __int64 __fastcall ATL::CAtlMap<unsigned long,CSqmSessionMgr::SqmSessionContext *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CSqmSessionMgr::SqmSessionContext *>>::PickSize(
        __int64 a1,
        __int64 a2)
{
  double v2; // xmm1_8
  float v3; // xmm0_4
  unsigned __int64 v4; // rcx
  double v5; // xmm1_8
  int v6; // edx
  unsigned __int64 result; // rax

  if ( a2 < 0 )
    v2 = (double)(int)(a2 & 1 | ((unsigned __int64)a2 >> 1)) + (double)(int)(a2 & 1 | ((unsigned __int64)a2 >> 1));
  else
    v2 = (double)(int)a2;
  v3 = *(float *)(a1 + 20);
  v4 = 0;
  v5 = v2 / v3;
  if ( v5 >= 9.223372036854776e18 )
  {
    v5 = v5 - 9.223372036854776e18;
    if ( v5 < 9.223372036854776e18 )
      v4 = 0x8000000000000000uLL;
  }
  v6 = 0;
  result = v4 + (unsigned int)(int)v5;
  if ( result > 0xFFFFFFFF )
  {
    result = 0xFFFFFFFFLL;
    goto LABEL_10;
  }
  if ( (unsigned int)result > 0x11 )
  {
    do
LABEL_10:
      ++v6;
    while ( (unsigned int)result > *((_DWORD *)`ATL::CAtlMap<unsigned long,CSqmSession::SqmTimerEntry *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CSqmSession::SqmTimerEntry *>>::PickSize'::`2'::s_anPrimes
                                   + v6) );
  }
  if ( *((_DWORD *)`ATL::CAtlMap<unsigned long,CSqmSession::SqmTimerEntry *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CSqmSession::SqmTimerEntry *>>::PickSize'::`2'::s_anPrimes
       + v6) != -1 )
    return *((unsigned int *)`ATL::CAtlMap<unsigned long,CSqmSession::SqmTimerEntry *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CSqmSession::SqmTimerEntry *>>::PickSize'::`2'::s_anPrimes
           + v6);
  return result;
}

```

## disassembly

```asm
0x180014978  xorps   xmm1, xmm1
0x18001497b  test    rdx, rdx
0x18001497e  js      short loc_180014987
0x180014980  cvtsi2sd xmm1, rdx
0x180014985  jmp     short loc_18001499C
0x180014987  mov     rax, rdx
0x18001498a  and     edx, 1
0x18001498d  shr     rax, 1
0x180014990  or      rax, rdx
0x180014993  cvtsi2sd xmm1, rax
0x180014998  addsd   xmm1, xmm1
0x18001499c  movss   xmm0, dword ptr [rcx+14h]
0x1800149a1  xor     ecx, ecx
0x1800149a3  cvtps2pd xmm0, xmm0
0x1800149a6  divsd   xmm1, xmm0
0x1800149aa  movsd   xmm0, cs:__real@43e0000000000000
0x1800149b2  comisd  xmm1, xmm0
0x1800149b6  jb      short loc_1800149CF
0x1800149b8  subsd   xmm1, xmm0
0x1800149bc  comisd  xmm1, xmm0
0x1800149c0  jnb     short loc_1800149CF
0x1800149c2  mov     rax, 8000000000000000h
0x1800149cc  mov     rcx, rax
0x1800149cf  cvttsd2si rax, xmm1
0x1800149d4  mov     r8d, 0FFFFFFFFh
0x1800149da  lea     r9, ?s_anPrimes@?1??PickSize@?$CAtlMap@KPEAVSqmTimerEntry@CSqmSession@@V?$CElementTraits@K@ATL@@V?$CElementTraits@PEAVSqmTimerEntry@CSqmSession@@@4@@ATL@@AEBAI_K@Z@4QBIB; uint const near * const `ATL::CAtlMap<ulong,CSqmSession::SqmTimerEntry *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CSqmSession::SqmTimerEntry *>>::PickSize(unsigned __int64)'::`2'::s_anPrimes
0x1800149e1  xor     edx, edx
0x1800149e3  add     rax, rcx
0x1800149e6  cmp     rax, r8
0x1800149e9  jbe     short loc_1800149F0
0x1800149eb  mov     eax, r8d
0x1800149ee  jmp     short loc_1800149F5
0x1800149f0  cmp     eax, 11h
0x1800149f3  jbe     short loc_180014A00
0x1800149f5  inc     edx
0x1800149f7  movsxd  rcx, edx
0x1800149fa  cmp     eax, [r9+rcx*4]
0x1800149fe  ja      short loc_1800149F5
0x180014a00  movsxd  rcx, edx
0x180014a03  cmp     [r9+rcx*4], r8d
0x180014a07  cmovnz  eax, [r9+rcx*4]
0x180014a0c  retn
```
