# ReadObservanceInfo

- ea: `0x18001a45c`
- end: `0x18001a848`
- name: `ReadObservanceInfo`
- size: `1004`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18001905c`

## callees

- `0x180018eec`
- `0x180019590`
- `0x180019940`
- `0x180019b5c`
- `0x18001a084`
- `0x18001a45c`
- `0x18001b0ea`
- `0x18001b0f6`
- `0x18001b150`

## import_xrefs

- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001a53d`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001a5b8`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001a708`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001a7a5`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001a53d`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001a5b8`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001a708`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18001a7a5`

## pseudocode

```c
__int64 __fastcall ReadObservanceInfo(unsigned __int64 *a1, __int64 a2, __int64 a3, _DWORD *a4, _DWORD *a5, __int64 a6)
{
  int NoDstStart; // edi
  __int64 v11; // rax
  int v12; // r9d
  unsigned __int64 v13; // r8
  unsigned __int64 v14; // rcx
  int v15; // eax
  int v16; // r9d
  int v17; // eax
  bool v18; // cc
  __int64 v19; // rcx
  __m128i v20; // xmm2
  __int128 v21; // xmm1
  __int16 v22; // ax
  __int128 v23; // xmm0
  int v24; // eax
  int v25; // edx
  int v26; // r8d
  DWORD v27; // r8d
  __int64 v28; // rax
  bool v29; // zf
  __int64 v30; // rdx
  int v31; // edx
  __int64 v32; // rax
  FILETIME v34[2]; // [rsp+30h] [rbp-79h] BYREF
  FILETIME FileTime; // [rsp+40h] [rbp-69h] BYREF
  __int128 v36; // [rsp+48h] [rbp-61h] BYREF
  __int64 v37; // [rsp+58h] [rbp-51h]
  _OWORD v38[2]; // [rsp+60h] [rbp-49h] BYREF
  __int128 Buf1; // [rsp+80h] [rbp-29h] BYREF
  __int128 Buf2; // [rsp+90h] [rbp-19h] BYREF
  __int64 v41; // [rsp+A0h] [rbp-9h]

  NoDstStart = 0;
  v11 = *(_QWORD *)(a2 + 32) - *(_QWORD *)(a2 + 48);
  if ( !v11 )
    v11 = *(_QWORD *)(a2 + 40) - *(_QWORD *)(a2 + 56);
  if ( !v11 )
  {
    *a5 = *(_DWORD *)(a2 + 20);
    if ( !a6 )
      return (unsigned int)NoDstStart;
    v34[0].dwLowDateTime = 0;
    *(_DWORD *)(a6 + 4) = 0;
    NoDstStart = GetNoDstStart(a2, 1, a6 + 8, v34);
    if ( NoDstStart < 0 )
      return (unsigned int)NoDstStart;
    *(_DWORD *)a6 = 0;
    if ( *(_WORD *)(a6 + 266) )
      *(_DWORD *)a6 = *a5 - v34[0].dwLowDateTime;
LABEL_46:
    v16 = 0;
    return (unsigned int)GetObservanceEnd(a2, a3, (int)a4, v16, (void *)(a6 + 284));
  }
  v12 = a4[2];
  v13 = *(_QWORD *)(a3 + 8) + 600000000LL * v12;
  v14 = *(_QWORD *)a3 + 600000000LL * a4[3];
  if ( v13 > *a1 )
  {
    if ( v14 > *a1 )
      goto LABEL_16;
  }
  else if ( !*(_DWORD *)(a3 + 16) || v14 > *a1 )
  {
    *a5 = a4[1];
    if ( a6 )
    {
      v15 = a4[1] - a4[2];
      *(_DWORD *)a6 = v15;
      NoDstStart = -2147467259;
      *(_DWORD *)(a6 + 4) = 1;
      FileTime = (FILETIME)(*(_QWORD *)(a3 + 8) + -600000000LL * v15);
      if ( FileTimeToSystemTime(&FileTime, (LPSYSTEMTIME)(a6 + 264)) )
      {
        v16 = 1;
        *(_DWORD *)(a6 + 280) = *a5;
        return (unsigned int)GetObservanceEnd(a2, a3, (int)a4, v16, (void *)(a6 + 284));
      }
    }
    return (unsigned int)NoDstStart;
  }
  if ( *(_DWORD *)(a3 + 16) || v13 > *a1 )
  {
    *a5 = *a4;
    if ( !a6 )
      return (unsigned int)NoDstStart;
    *(_DWORD *)(a6 + 4) = 0;
    NoDstStart = -2147467259;
    v17 = *a4 - a4[3];
    *(_DWORD *)a6 = v17;
    FileTime = (FILETIME)(*(_QWORD *)a3 + -600000000LL * v17);
    *(_DWORD *)(a6 + 280) = *a5;
    if ( !FileTimeToSystemTime(&FileTime, (LPSYSTEMTIME)(a6 + 264)) )
      return (unsigned int)NoDstStart;
    goto LABEL_46;
  }
LABEL_16:
  if ( *(_DWORD *)(a3 + 16) )
  {
    v18 = v13 <= *a1;
  }
  else
  {
    v12 = a4[3];
    v18 = v14 <= *a1;
  }
  if ( v18 )
    return (unsigned int)-2147467259;
  *a5 = v12;
  if ( a6 )
  {
    *(_DWORD *)((char *)v38 + 2) = 0;
    WORD3(v38[0]) = 0;
    memset_0(v38, 0, 0x42u);
    if ( (unsigned int)CanCheckPreviousEntry(a2) )
    {
      NoDstStart = GetDstDataForPreviousYear(v19, v38);
    }
    else
    {
      v20 = *(__m128i *)a2;
      v21 = *(_OWORD *)(a2 + 32);
      v22 = _mm_cvtsi128_si32(*(__m128i *)a2);
      v38[1] = *(_OWORD *)(a2 + 16);
      v23 = *(_OWORD *)(a2 + 48);
      Buf1 = v21;
      *(_QWORD *)&v21 = *(_QWORD *)(a2 + 64);
      v38[0] = v20;
      LOWORD(v38[0]) = v22 - 1;
      Buf2 = v23;
      v41 = v21;
    }
    if ( NoDstStart >= 0 )
    {
      v37 = 0;
      v36 = 0;
      *(_OWORD *)&v34[0].dwLowDateTime = 0;
      NoDstStart = GetTransitionInfo(v38, &v36, v34);
      if ( NoDstStart >= 0 )
      {
        v24 = memcmp_0(&Buf1, &Buf2, 0x10u);
        v25 = 0;
        if ( v24 )
        {
          v26 = *a5;
          if ( (_DWORD)v37 )
          {
            v27 = v26 - v34[0].dwHighDateTime;
            v28 = v36 + 10000000LL * (int)(-60 * v27);
          }
          else
          {
            v27 = v26 - v34[0].dwLowDateTime;
            v25 = 1;
            v28 = *((_QWORD *)&v36 + 1) + 10000000LL * (int)(-60 * v27);
          }
          *(_DWORD *)a6 = v27;
          *(_DWORD *)(a6 + 4) = v25;
          v34[0] = (FILETIME)v28;
          *(_DWORD *)(a6 + 280) = *a5;
          if ( !FileTimeToSystemTime(v34, (LPSYSTEMTIME)(a6 + 264)) )
            NoDstStart = -2147467259;
          if ( NoDstStart < 0 )
            return (unsigned int)NoDstStart;
        }
        else
        {
          v29 = *(_DWORD *)(a3 + 16) == 0;
          v34[0].dwLowDateTime = 0;
          v30 = (unsigned int)v37;
          *(_DWORD *)(a6 + 4) = v29;
          NoDstStart = GetNoDstStart(a2, v30, a6 + 8, v34);
          if ( NoDstStart < 0 )
            return (unsigned int)NoDstStart;
          *(_DWORD *)a6 = *a5 - v34[0].dwLowDateTime;
        }
        if ( *(_DWORD *)(a3 + 16) )
        {
          v31 = a4[1];
          v32 = *(_QWORD *)(a3 + 8) + 600000000LL * (a4[2] - v31);
        }
        else
        {
          v31 = *a4;
          v32 = *(_QWORD *)a3 + 600000000LL * (a4[3] - *a4);
        }
        v34[0] = (FILETIME)v32;
        *(_DWORD *)(a6 + 556) = v31;
        if ( !FileTimeToSystemTime(v34, (LPSYSTEMTIME)(a6 + 540)) )
          return (unsigned int)-2147467259;
      }
    }
  }
  return (unsigned int)NoDstStart;
}

```

## disassembly

```asm
0x18001a45c  mov     [rsp-8+arg_0], rbx
0x18001a461  push    rbp
0x18001a462  push    rsi
0x18001a463  push    rdi
0x18001a464  push    r12
0x18001a466  push    r13
0x18001a468  push    r14
0x18001a46a  push    r15
0x18001a46c  lea     rbp, [rsp-17h]
0x18001a471  sub     rsp, 0C0h
0x18001a478  mov     rax, cs:__security_cookie
0x18001a47f  xor     rax, rsp
0x18001a482  mov     [rbp+47h+var_40], rax
0x18001a486  mov     rax, [rdx+20h]
0x18001a48a  xor     r13d, r13d
0x18001a48d  mov     r15, r9
0x18001a490  mov     rbx, [rbp+47h+arg_28]
0x18001a494  mov     r14, r8
0x18001a497  mov     r12, [rbp+47h+arg_20]
0x18001a49b  mov     rsi, rdx
0x18001a49e  mov     r10, rcx
0x18001a4a1  mov     edi, r13d
0x18001a4a4  sub     rax, [rdx+30h]
0x18001a4a8  jnz     short loc_18001A4B2
0x18001a4aa  mov     rax, [rdx+28h]
0x18001a4ae  sub     rax, [rdx+38h]
0x18001a4b2  test    rax, rax
0x18001a4b5  jz      loc_18001A7BB
0x18001a4bb  mov     r9d, [r9+8]
0x18001a4bf  imul    eax, r9d, 3Ch ; '<'
0x18001a4c3  movsxd  rcx, eax
0x18001a4c6  imul    eax, [r15+0Ch], 3Ch ; '<'
0x18001a4cb  imul    r8, rcx, 989680h
0x18001a4d2  movsxd  rcx, eax
0x18001a4d5  add     r8, [r14+8]
0x18001a4d9  imul    rcx, 989680h
0x18001a4e0  add     rcx, [r14]
0x18001a4e3  cmp     r8, [r10]
0x18001a4e6  ja      short loc_18001A55D
0x18001a4e8  cmp     [r14+10h], r13d
0x18001a4ec  jz      short loc_18001A4F3
0x18001a4ee  cmp     rcx, [r10]
0x18001a4f1  jbe     short loc_18001A562
0x18001a4f3  mov     eax, [r15+4]
0x18001a4f7  mov     [r12], eax
0x18001a4fb  test    rbx, rbx
0x18001a4fe  jz      loc_18001A81F
0x18001a504  mov     eax, [r15+4]
0x18001a508  lea     rdx, [rbx+108h]; lpSystemTime
0x18001a50f  sub     eax, [r15+8]
0x18001a513  mov     r13d, 1
0x18001a519  mov     [rbx], eax
0x18001a51b  mov     edi, 80004005h
0x18001a520  imul    eax, -3Ch
0x18001a523  mov     [rbx+4], r13d
0x18001a527  movsxd  rcx, eax
0x18001a52a  imul    rax, rcx, 989680h
0x18001a531  lea     rcx, [rbp+47h+FileTime]; lpFileTime
0x18001a535  add     rax, [r14+8]
0x18001a539  mov     qword ptr [rbp+47h+FileTime.dwLowDateTime], rax
0x18001a53d  call    cs:__imp_FileTimeToSystemTime
0x18001a543  test    eax, eax
0x18001a545  jz      loc_18001A81F
0x18001a54b  mov     eax, [r12]
0x18001a54f  mov     r9d, r13d
0x18001a552  mov     [rbx+118h], eax
0x18001a558  jmp     loc_18001A803
0x18001a55d  cmp     rcx, [r10]
0x18001a560  ja      short loc_18001A5CB
0x18001a562  cmp     [r14+10h], r13d
0x18001a566  jnz     short loc_18001A56D
0x18001a568  cmp     r8, [r10]
0x18001a56b  jbe     short loc_18001A5CB
0x18001a56d  mov     eax, [r15]
0x18001a570  mov     [r12], eax
0x18001a574  test    rbx, rbx
0x18001a577  jz      loc_18001A81F
0x18001a57d  mov     [rbx+4], r13d
0x18001a581  lea     rdx, [rbx+108h]; lpSystemTime
0x18001a588  mov     eax, [r15]
0x18001a58b  mov     edi, 80004005h
0x18001a590  sub     eax, [r15+0Ch]
0x18001a594  mov     [rbx], eax
0x18001a596  imul    eax, -3Ch
0x18001a599  movsxd  rcx, eax
0x18001a59c  imul    rax, rcx, 989680h
0x18001a5a3  lea     rcx, [rbp+47h+FileTime]; lpFileTime
0x18001a5a7  add     rax, [r14]
0x18001a5aa  mov     qword ptr [rbp+47h+FileTime.dwLowDateTime], rax
0x18001a5ae  mov     eax, [r12]
0x18001a5b2  mov     [rbx+118h], eax
0x18001a5b8  call    cs:__imp_FileTimeToSystemTime
0x18001a5be  test    eax, eax
0x18001a5c0  jz      loc_18001A81F
0x18001a5c6  jmp     loc_18001A800
0x18001a5cb  cmp     [r14+10h], r13d
0x18001a5cf  jz      short loc_18001A5D6
0x18001a5d1  cmp     r8, [r10]
0x18001a5d4  jmp     short loc_18001A5DD
0x18001a5d6  mov     r9d, [r15+0Ch]
0x18001a5da  cmp     rcx, [r10]
0x18001a5dd  jbe     loc_18001A7B4
0x18001a5e3  mov     [r12], r9d
0x18001a5e7  test    rbx, rbx
0x18001a5ea  jz      loc_18001A81F
0x18001a5f0  xor     eax, eax
0x18001a5f2  lea     rcx, [rbp+47h+var_90]; void *
0x18001a5f6  xor     edx, edx; Val
0x18001a5f8  mov     dword ptr [rbp+47h+var_90+2], eax
0x18001a5fb  mov     word ptr [rbp+47h+var_90+6], ax
0x18001a5ff  lea     r8d, [rax+42h]; Size
0x18001a603  call    memset_0
0x18001a608  mov     rcx, rsi
0x18001a60b  call    CanCheckPreviousEntry
0x18001a610  test    eax, eax
0x18001a612  jz      short loc_18001A621
0x18001a614  lea     rdx, [rbp+47h+var_90]
0x18001a618  call    GetDstDataForPreviousYear
0x18001a61d  mov     edi, eax
0x18001a61f  jmp     short loc_18001A65A
0x18001a621  movups  xmm2, xmmword ptr [rsi]
0x18001a624  mov     ecx, 0FFFFh
0x18001a629  movups  xmm0, xmmword ptr [rsi+10h]
0x18001a62d  movups  xmm1, xmmword ptr [rsi+20h]
0x18001a631  movd    eax, xmm2
0x18001a635  movaps  [rbp+47h+var_80], xmm0
0x18001a639  movups  xmm0, xmmword ptr [rsi+30h]
0x18001a63d  add     ax, cx
0x18001a640  movaps  [rbp+47h+Buf1], xmm1
0x18001a644  movsd   xmm1, qword ptr [rsi+40h]
0x18001a649  movaps  [rbp+47h+var_90], xmm2
0x18001a64d  mov     word ptr [rbp+47h+var_90], ax
0x18001a651  movaps  [rbp+47h+Buf2], xmm0
0x18001a655  movsd   [rbp+47h+var_50], xmm1
0x18001a65a  test    edi, edi
0x18001a65c  js      loc_18001A81F
0x18001a662  xorps   xmm0, xmm0
0x18001a665  lea     r8, [rbp+47h+var_C0]
0x18001a669  xor     eax, eax
0x18001a66b  lea     rdx, [rbp+47h+var_A8]
0x18001a66f  lea     rcx, [rbp+47h+var_90]
0x18001a673  mov     [rbp+47h+var_98], rax
0x18001a677  movups  [rbp+47h+var_A8], xmm0
0x18001a67b  movups  xmmword ptr [rbp+47h+var_C0.dwLowDateTime], xmm0
0x18001a67f  call    GetTransitionInfo
0x18001a684  mov     edi, eax
0x18001a686  test    eax, eax
0x18001a688  js      loc_18001A81F
0x18001a68e  mov     r8d, 10h; Size
0x18001a694  lea     rdx, [rbp+47h+Buf2]; Buf2
0x18001a698  lea     rcx, [rbp+47h+Buf1]; Buf1
0x18001a69c  call    memcmp_0
0x18001a6a1  xor     edx, edx
0x18001a6a3  mov     r13d, 80004005h
0x18001a6a9  test    eax, eax
0x18001a6ab  jz      short loc_18001A71E
0x18001a6ad  mov     r8d, [r12]
0x18001a6b1  cmp     dword ptr [rbp+47h+var_98], edx
0x18001a6b4  jz      short loc_18001A6CE
0x18001a6b6  sub     r8d, [rbp+47h+var_C0.dwHighDateTime]
0x18001a6ba  imul    eax, r8d, -3Ch
0x18001a6be  movsxd  rcx, eax
0x18001a6c1  imul    rax, rcx, 989680h
0x18001a6c8  add     rax, qword ptr [rbp+47h+var_A8]
0x18001a6cc  jmp     short loc_18001A6E9
0x18001a6ce  sub     r8d, [rbp+47h+var_C0.dwLowDateTime]
0x18001a6d2  mov     edx, 1
0x18001a6d7  imul    eax, r8d, -3Ch
0x18001a6db  movsxd  rcx, eax
0x18001a6de  imul    rax, rcx, 989680h
0x18001a6e5  add     rax, qword ptr [rbp+47h+var_A8+8]
0x18001a6e9  mov     [rbx], r8d
0x18001a6ec  lea     rcx, [rbp+47h+var_C0]; lpFileTime
0x18001a6f0  mov     [rbx+4], edx
0x18001a6f3  lea     rdx, [rbx+108h]; lpSystemTime
0x18001a6fa  mov     qword ptr [rbp+47h+var_C0.dwLowDateTime], rax
0x18001a6fe  mov     eax, [r12]
0x18001a702  mov     [rbx+118h], eax
0x18001a708  call    cs:__imp_FileTimeToSystemTime
0x18001a70e  test    eax, eax
0x18001a710  cmovz   edi, r13d
0x18001a714  test    edi, edi
0x18001a716  js      loc_18001A81F
0x18001a71c  jmp     short loc_18001A753
0x18001a71e  cmp     [r14+10h], edx
0x18001a722  lea     r8, [rbx+8]
0x18001a726  mov     eax, edx
0x18001a728  mov     [rbp+47h+var_C0.dwLowDateTime], edx
0x18001a72b  mov     edx, dword ptr [rbp+47h+var_98]
0x18001a72e  lea     r9, [rbp+47h+var_C0]
0x18001a732  setz    al
0x18001a735  mov     rcx, rsi
0x18001a738  mov     [rbx+4], eax
0x18001a73b  call    GetNoDstStart
0x18001a740  mov     edi, eax
0x18001a742  test    eax, eax
0x18001a744  js      loc_18001A81F
0x18001a74a  mov     eax, [r12]
0x18001a74e  sub     eax, [rbp+47h+var_C0.dwLowDateTime]
0x18001a751  mov     [rbx], eax
0x18001a753  cmp     dword ptr [r14+10h], 0
0x18001a758  jz      short loc_18001A777
0x18001a75a  mov     eax, [r15+8]
0x18001a75e  mov     edx, [r15+4]
0x18001a762  sub     eax, edx
0x18001a764  imul    eax, 3Ch ; '<'
0x18001a767  movsxd  rcx, eax
0x18001a76a  imul    rax, rcx, 989680h
0x18001a771  add     rax, [r14+8]
0x18001a775  jmp     short loc_18001A790
0x18001a777  mov     eax, [r15+0Ch]
0x18001a77b  mov     edx, [r15]
0x18001a77e  sub     eax, edx
0x18001a780  imul    eax, 3Ch ; '<'
0x18001a783  movsxd  rcx, eax
0x18001a786  imul    rax, rcx, 989680h
0x18001a78d  add     rax, [r14]
0x18001a790  mov     qword ptr [rbp+47h+var_C0.dwLowDateTime], rax
0x18001a794  lea     rcx, [rbp+47h+var_C0]; lpFileTime
0x18001a798  mov     [rbx+22Ch], edx
0x18001a79e  lea     rdx, [rbx+21Ch]; lpSystemTime
0x18001a7a5  call    cs:__imp_FileTimeToSystemTime
0x18001a7ab  test    eax, eax
0x18001a7ad  jnz     short loc_18001A81F
0x18001a7af  mov     edi, r13d
0x18001a7b2  jmp     short loc_18001A81F
0x18001a7b4  mov     edi, 80004005h
0x18001a7b9  jmp     short loc_18001A81F
0x18001a7bb  mov     eax, [rdx+14h]
0x18001a7be  mov     [r12], eax
0x18001a7c2  test    rbx, rbx
0x18001a7c5  jz      short loc_18001A81F
0x18001a7c7  lea     r8, [rbx+8]
0x18001a7cb  mov     [rbp+47h+var_C0.dwLowDateTime], r13d
0x18001a7cf  lea     r9, [rbp+47h+var_C0]
0x18001a7d3  mov     [rbx+4], r13d
0x18001a7d7  mov     edx, 1
0x18001a7dc  mov     rcx, rsi
0x18001a7df  call    GetNoDstStart
0x18001a7e4  mov     edi, eax
0x18001a7e6  test    eax, eax
0x18001a7e8  js      short loc_18001A81F
0x18001a7ea  mov     [rbx], r13d
0x18001a7ed  cmp     [rbx+10Ah], r13w
0x18001a7f5  jz      short loc_18001A800
0x18001a7f7  mov     eax, [r12]
0x18001a7fb  sub     eax, [rbp+47h+var_C0.dwLowDateTime]
0x18001a7fe  mov     [rbx], eax
0x18001a800  xor     r9d, r9d; int
0x18001a803  lea     rax, [rbx+11Ch]
0x18001a80a  mov     r8, r15; int
0x18001a80d  mov     rdx, r14; int
0x18001a810  mov     [rsp+0F0h+var_D0], rax; void *
0x18001a815  mov     rcx, rsi; int
0x18001a818  call    GetObservanceEnd
0x18001a81d  mov     edi, eax
0x18001a81f  mov     eax, edi
0x18001a821  mov     rcx, [rbp+47h+var_40]
0x18001a825  xor     rcx, rsp; StackCookie
0x18001a828  call    __security_check_cookie
0x18001a82d  mov     rbx, [rsp+0F0h+arg_0]
0x18001a835  add     rsp, 0C0h
0x18001a83c  pop     r15
0x18001a83e  pop     r14
0x18001a840  pop     r13
0x18001a842  pop     r12
0x18001a844  pop     rdi
0x18001a845  pop     rsi
0x18001a846  pop     rbp
0x18001a847  retn
```
