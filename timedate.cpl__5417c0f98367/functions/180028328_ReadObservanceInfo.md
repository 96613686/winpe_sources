# ReadObservanceInfo

- ea: `0x180028328`
- end: `0x180028714`
- name: `ReadObservanceInfo`
- size: `1004`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180026ed8`

## callees

- `0x180026c8c`
- `0x180027420`
- `0x1800277d8`
- `0x1800279f4`
- `0x180027f44`
- `0x180028328`
- `0x180028f16`
- `0x180028f2e`
- `0x180028f60`

## import_xrefs

- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180028409`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180028484`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800285d4`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180028671`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180028409`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180028484`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800285d4`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180028671`

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
0x180028328  mov     [rsp-8+arg_0], rbx
0x18002832d  push    rbp
0x18002832e  push    rsi
0x18002832f  push    rdi
0x180028330  push    r12
0x180028332  push    r13
0x180028334  push    r14
0x180028336  push    r15
0x180028338  lea     rbp, [rsp-17h]
0x18002833d  sub     rsp, 0C0h
0x180028344  mov     rax, cs:__security_cookie
0x18002834b  xor     rax, rsp
0x18002834e  mov     [rbp+47h+var_40], rax
0x180028352  mov     rax, [rdx+20h]
0x180028356  xor     r13d, r13d
0x180028359  mov     r15, r9
0x18002835c  mov     rbx, [rbp+47h+arg_28]
0x180028360  mov     r14, r8
0x180028363  mov     r12, [rbp+47h+arg_20]
0x180028367  mov     rsi, rdx
0x18002836a  mov     r10, rcx
0x18002836d  mov     edi, r13d
0x180028370  sub     rax, [rdx+30h]
0x180028374  jnz     short loc_18002837E
0x180028376  mov     rax, [rdx+28h]
0x18002837a  sub     rax, [rdx+38h]
0x18002837e  test    rax, rax
0x180028381  jz      loc_180028687
0x180028387  mov     r9d, [r9+8]
0x18002838b  imul    eax, r9d, 3Ch ; '<'
0x18002838f  movsxd  rcx, eax
0x180028392  imul    eax, [r15+0Ch], 3Ch ; '<'
0x180028397  imul    r8, rcx, 989680h
0x18002839e  movsxd  rcx, eax
0x1800283a1  add     r8, [r14+8]
0x1800283a5  imul    rcx, 989680h
0x1800283ac  add     rcx, [r14]
0x1800283af  cmp     r8, [r10]
0x1800283b2  ja      short loc_180028429
0x1800283b4  cmp     [r14+10h], r13d
0x1800283b8  jz      short loc_1800283BF
0x1800283ba  cmp     rcx, [r10]
0x1800283bd  jbe     short loc_18002842E
0x1800283bf  mov     eax, [r15+4]
0x1800283c3  mov     [r12], eax
0x1800283c7  test    rbx, rbx
0x1800283ca  jz      loc_1800286EB
0x1800283d0  mov     eax, [r15+4]
0x1800283d4  lea     rdx, [rbx+108h]; lpSystemTime
0x1800283db  sub     eax, [r15+8]
0x1800283df  mov     r13d, 1
0x1800283e5  mov     [rbx], eax
0x1800283e7  mov     edi, 80004005h
0x1800283ec  imul    eax, -3Ch
0x1800283ef  mov     [rbx+4], r13d
0x1800283f3  movsxd  rcx, eax
0x1800283f6  imul    rax, rcx, 989680h
0x1800283fd  lea     rcx, [rbp+47h+FileTime]; lpFileTime
0x180028401  add     rax, [r14+8]
0x180028405  mov     qword ptr [rbp+47h+FileTime.dwLowDateTime], rax
0x180028409  call    cs:__imp_FileTimeToSystemTime
0x18002840f  test    eax, eax
0x180028411  jz      loc_1800286EB
0x180028417  mov     eax, [r12]
0x18002841b  mov     r9d, r13d
0x18002841e  mov     [rbx+118h], eax
0x180028424  jmp     loc_1800286CF
0x180028429  cmp     rcx, [r10]
0x18002842c  ja      short loc_180028497
0x18002842e  cmp     [r14+10h], r13d
0x180028432  jnz     short loc_180028439
0x180028434  cmp     r8, [r10]
0x180028437  jbe     short loc_180028497
0x180028439  mov     eax, [r15]
0x18002843c  mov     [r12], eax
0x180028440  test    rbx, rbx
0x180028443  jz      loc_1800286EB
0x180028449  mov     [rbx+4], r13d
0x18002844d  lea     rdx, [rbx+108h]; lpSystemTime
0x180028454  mov     eax, [r15]
0x180028457  mov     edi, 80004005h
0x18002845c  sub     eax, [r15+0Ch]
0x180028460  mov     [rbx], eax
0x180028462  imul    eax, -3Ch
0x180028465  movsxd  rcx, eax
0x180028468  imul    rax, rcx, 989680h
0x18002846f  lea     rcx, [rbp+47h+FileTime]; lpFileTime
0x180028473  add     rax, [r14]
0x180028476  mov     qword ptr [rbp+47h+FileTime.dwLowDateTime], rax
0x18002847a  mov     eax, [r12]
0x18002847e  mov     [rbx+118h], eax
0x180028484  call    cs:__imp_FileTimeToSystemTime
0x18002848a  test    eax, eax
0x18002848c  jz      loc_1800286EB
0x180028492  jmp     loc_1800286CC
0x180028497  cmp     [r14+10h], r13d
0x18002849b  jz      short loc_1800284A2
0x18002849d  cmp     r8, [r10]
0x1800284a0  jmp     short loc_1800284A9
0x1800284a2  mov     r9d, [r15+0Ch]
0x1800284a6  cmp     rcx, [r10]
0x1800284a9  jbe     loc_180028680
0x1800284af  mov     [r12], r9d
0x1800284b3  test    rbx, rbx
0x1800284b6  jz      loc_1800286EB
0x1800284bc  xor     eax, eax
0x1800284be  lea     rcx, [rbp+47h+var_90]; void *
0x1800284c2  xor     edx, edx; Val
0x1800284c4  mov     dword ptr [rbp+47h+var_90+2], eax
0x1800284c7  mov     word ptr [rbp+47h+var_90+6], ax
0x1800284cb  lea     r8d, [rax+42h]; Size
0x1800284cf  call    memset_0
0x1800284d4  mov     rcx, rsi
0x1800284d7  call    CanCheckPreviousEntry
0x1800284dc  test    eax, eax
0x1800284de  jz      short loc_1800284ED
0x1800284e0  lea     rdx, [rbp+47h+var_90]
0x1800284e4  call    GetDstDataForPreviousYear
0x1800284e9  mov     edi, eax
0x1800284eb  jmp     short loc_180028526
0x1800284ed  movups  xmm2, xmmword ptr [rsi]
0x1800284f0  mov     ecx, 0FFFFh
0x1800284f5  movups  xmm0, xmmword ptr [rsi+10h]
0x1800284f9  movups  xmm1, xmmword ptr [rsi+20h]
0x1800284fd  movd    eax, xmm2
0x180028501  movaps  [rbp+47h+var_80], xmm0
0x180028505  movups  xmm0, xmmword ptr [rsi+30h]
0x180028509  add     ax, cx
0x18002850c  movaps  [rbp+47h+Buf1], xmm1
0x180028510  movsd   xmm1, qword ptr [rsi+40h]
0x180028515  movaps  [rbp+47h+var_90], xmm2
0x180028519  mov     word ptr [rbp+47h+var_90], ax
0x18002851d  movaps  [rbp+47h+Buf2], xmm0
0x180028521  movsd   [rbp+47h+var_50], xmm1
0x180028526  test    edi, edi
0x180028528  js      loc_1800286EB
0x18002852e  xorps   xmm0, xmm0
0x180028531  lea     r8, [rbp+47h+var_C0]
0x180028535  xor     eax, eax
0x180028537  lea     rdx, [rbp+47h+var_A8]
0x18002853b  lea     rcx, [rbp+47h+var_90]
0x18002853f  mov     [rbp+47h+var_98], rax
0x180028543  movups  [rbp+47h+var_A8], xmm0
0x180028547  movups  xmmword ptr [rbp+47h+var_C0.dwLowDateTime], xmm0
0x18002854b  call    GetTransitionInfo
0x180028550  mov     edi, eax
0x180028552  test    eax, eax
0x180028554  js      loc_1800286EB
0x18002855a  mov     r8d, 10h; Size
0x180028560  lea     rdx, [rbp+47h+Buf2]; Buf2
0x180028564  lea     rcx, [rbp+47h+Buf1]; Buf1
0x180028568  call    memcmp_0
0x18002856d  xor     edx, edx
0x18002856f  mov     r13d, 80004005h
0x180028575  test    eax, eax
0x180028577  jz      short loc_1800285EA
0x180028579  mov     r8d, [r12]
0x18002857d  cmp     dword ptr [rbp+47h+var_98], edx
0x180028580  jz      short loc_18002859A
0x180028582  sub     r8d, [rbp+47h+var_C0.dwHighDateTime]
0x180028586  imul    eax, r8d, -3Ch
0x18002858a  movsxd  rcx, eax
0x18002858d  imul    rax, rcx, 989680h
0x180028594  add     rax, qword ptr [rbp+47h+var_A8]
0x180028598  jmp     short loc_1800285B5
0x18002859a  sub     r8d, [rbp+47h+var_C0.dwLowDateTime]
0x18002859e  mov     edx, 1
0x1800285a3  imul    eax, r8d, -3Ch
0x1800285a7  movsxd  rcx, eax
0x1800285aa  imul    rax, rcx, 989680h
0x1800285b1  add     rax, qword ptr [rbp+47h+var_A8+8]
0x1800285b5  mov     [rbx], r8d
0x1800285b8  lea     rcx, [rbp+47h+var_C0]; lpFileTime
0x1800285bc  mov     [rbx+4], edx
0x1800285bf  lea     rdx, [rbx+108h]; lpSystemTime
0x1800285c6  mov     qword ptr [rbp+47h+var_C0.dwLowDateTime], rax
0x1800285ca  mov     eax, [r12]
0x1800285ce  mov     [rbx+118h], eax
0x1800285d4  call    cs:__imp_FileTimeToSystemTime
0x1800285da  test    eax, eax
0x1800285dc  cmovz   edi, r13d
0x1800285e0  test    edi, edi
0x1800285e2  js      loc_1800286EB
0x1800285e8  jmp     short loc_18002861F
0x1800285ea  cmp     [r14+10h], edx
0x1800285ee  lea     r8, [rbx+8]
0x1800285f2  mov     eax, edx
0x1800285f4  mov     [rbp+47h+var_C0.dwLowDateTime], edx
0x1800285f7  mov     edx, dword ptr [rbp+47h+var_98]
0x1800285fa  lea     r9, [rbp+47h+var_C0]
0x1800285fe  setz    al
0x180028601  mov     rcx, rsi
0x180028604  mov     [rbx+4], eax
0x180028607  call    GetNoDstStart
0x18002860c  mov     edi, eax
0x18002860e  test    eax, eax
0x180028610  js      loc_1800286EB
0x180028616  mov     eax, [r12]
0x18002861a  sub     eax, [rbp+47h+var_C0.dwLowDateTime]
0x18002861d  mov     [rbx], eax
0x18002861f  cmp     dword ptr [r14+10h], 0
0x180028624  jz      short loc_180028643
0x180028626  mov     eax, [r15+8]
0x18002862a  mov     edx, [r15+4]
0x18002862e  sub     eax, edx
0x180028630  imul    eax, 3Ch ; '<'
0x180028633  movsxd  rcx, eax
0x180028636  imul    rax, rcx, 989680h
0x18002863d  add     rax, [r14+8]
0x180028641  jmp     short loc_18002865C
0x180028643  mov     eax, [r15+0Ch]
0x180028647  mov     edx, [r15]
0x18002864a  sub     eax, edx
0x18002864c  imul    eax, 3Ch ; '<'
0x18002864f  movsxd  rcx, eax
0x180028652  imul    rax, rcx, 989680h
0x180028659  add     rax, [r14]
0x18002865c  mov     qword ptr [rbp+47h+var_C0.dwLowDateTime], rax
0x180028660  lea     rcx, [rbp+47h+var_C0]; lpFileTime
0x180028664  mov     [rbx+22Ch], edx
0x18002866a  lea     rdx, [rbx+21Ch]; lpSystemTime
0x180028671  call    cs:__imp_FileTimeToSystemTime
0x180028677  test    eax, eax
0x180028679  jnz     short loc_1800286EB
0x18002867b  mov     edi, r13d
0x18002867e  jmp     short loc_1800286EB
0x180028680  mov     edi, 80004005h
0x180028685  jmp     short loc_1800286EB
0x180028687  mov     eax, [rdx+14h]
0x18002868a  mov     [r12], eax
0x18002868e  test    rbx, rbx
0x180028691  jz      short loc_1800286EB
0x180028693  lea     r8, [rbx+8]
0x180028697  mov     [rbp+47h+var_C0.dwLowDateTime], r13d
0x18002869b  lea     r9, [rbp+47h+var_C0]
0x18002869f  mov     [rbx+4], r13d
0x1800286a3  mov     edx, 1
0x1800286a8  mov     rcx, rsi
0x1800286ab  call    GetNoDstStart
0x1800286b0  mov     edi, eax
0x1800286b2  test    eax, eax
0x1800286b4  js      short loc_1800286EB
0x1800286b6  mov     [rbx], r13d
0x1800286b9  cmp     [rbx+10Ah], r13w
0x1800286c1  jz      short loc_1800286CC
0x1800286c3  mov     eax, [r12]
0x1800286c7  sub     eax, [rbp+47h+var_C0.dwLowDateTime]
0x1800286ca  mov     [rbx], eax
0x1800286cc  xor     r9d, r9d; int
0x1800286cf  lea     rax, [rbx+11Ch]
0x1800286d6  mov     r8, r15; int
0x1800286d9  mov     rdx, r14; int
0x1800286dc  mov     [rsp+0F0h+var_D0], rax; void *
0x1800286e1  mov     rcx, rsi; int
0x1800286e4  call    GetObservanceEnd
0x1800286e9  mov     edi, eax
0x1800286eb  mov     eax, edi
0x1800286ed  mov     rcx, [rbp+47h+var_40]
0x1800286f1  xor     rcx, rsp; StackCookie
0x1800286f4  call    __security_check_cookie
0x1800286f9  mov     rbx, [rsp+0F0h+arg_0]
0x180028701  add     rsp, 0C0h
0x180028708  pop     r15
0x18002870a  pop     r14
0x18002870c  pop     r13
0x18002870e  pop     r12
0x180028710  pop     rdi
0x180028711  pop     rsi
0x180028712  pop     rbp
0x180028713  retn
```
