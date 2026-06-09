# rtStandardSplit

- ea: `0x1800196f0`
- end: `0x180019d3d`
- name: `rtStandardSplit`
- size: `1613`
- prototype: `__int64 __fastcall(const OLECHAR *lpWideCharStr, BSTR, int, LCID, int, SAFEARRAY **)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180017c30`
- `0x180025df0`

## callees

- `0x1800196f0`
- `0x180035500`
- `0x180061cd8`
- `0x180079412`
- `0x180079490`

## import_xrefs

- `msvcrt!malloc` at `0x180019c05`
- `msvcrt!malloc` at `0x180019c05`
- `msvcrt!free` at `0x180019a80`
- `msvcrt!free` at `0x180019cf0`
- `msvcrt!free` at `0x180019a80`
- `msvcrt!free` at `0x180019cf0`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800198ce`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800198ce`
- `OLEAUT32!__imp_SysFreeString` at `0x180019d18`
- `OLEAUT32!__imp_SysFreeString` at `0x180019d2c`
- `OLEAUT32!__imp_SysFreeString` at `0x180019d18`
- `OLEAUT32!__imp_SysFreeString` at `0x180019d2c`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180019858`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180019858`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180019d04`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180019d04`

## pseudocode

```c
__int64 __fastcall rtStandardSplit(const OLECHAR *lpWideCharStr, BSTR a2, int a3, LCID a4, int a5, SAFEARRAY **a6)
{
  OLECHAR *v6; // r15
  SAFEARRAY *v9; // rsi
  LPCWCH v10; // rdx
  signed int v11; // r13d
  unsigned int v12; // r10d
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // r15d
  unsigned int v16; // r15d
  int v17; // esi
  OLECHAR v18; // si
  const WCHAR *v19; // rdi
  const WCHAR *v20; // r14
  __int64 i; // rax
  const WCHAR *v22; // rbx
  signed int v23; // edi
  signed int v24; // ebx
  SAFEARRAY *v25; // rax
  _QWORD *pvData; // r12
  unsigned int v27; // r14d
  const OLECHAR *v28; // r13
  unsigned int v29; // eax
  unsigned int v30; // eax
  __int64 v31; // rsi
  __int64 v32; // rax
  BSTR v33; // r8
  struct ExpPosition *v34; // r14
  __int64 v35; // rbx
  unsigned int v36; // edi
  unsigned int v37; // ebx
  _DWORD *v38; // r9
  unsigned int v39; // r8d
  unsigned int v40; // ecx
  unsigned int m; // edx
  char *v42; // r9
  unsigned int v43; // edi
  unsigned int n; // ecx
  int v45; // ebx
  unsigned int v47; // edx
  unsigned int v48; // edx
  unsigned int j; // ecx
  unsigned int v50; // edx
  unsigned int k; // ecx
  int v52; // esi
  _OWORD *v53; // rax
  int v54; // [rsp+30h] [rbp-D0h]
  unsigned int v55; // [rsp+34h] [rbp-CCh]
  unsigned int v56; // [rsp+38h] [rbp-C8h]
  unsigned int v57; // [rsp+3Ch] [rbp-C4h] BYREF
  BSTR v58; // [rsp+40h] [rbp-C0h] BYREF
  void *Block; // [rsp+48h] [rbp-B8h] BYREF
  struct ExpPosition *v60; // [rsp+50h] [rbp-B0h] BYREF
  SAFEARRAY *v61; // [rsp+58h] [rbp-A8h]
  SAFEARRAYBOUND rgsabound; // [rsp+60h] [rbp-A0h] BYREF
  int v63; // [rsp+68h] [rbp-98h]
  unsigned int v64; // [rsp+6Ch] [rbp-94h]
  BSTR bstrString; // [rsp+70h] [rbp-90h] BYREF
  const WCHAR *v66; // [rsp+78h] [rbp-88h]
  const OLECHAR *v67; // [rsp+80h] [rbp-80h]
  SAFEARRAY **v68; // [rsp+88h] [rbp-78h]
  _OWORD v69[10]; // [rsp+90h] [rbp-70h] BYREF

  v6 = 0;
  v67 = lpWideCharStr;
  v9 = 0;
  v54 = a3;
  v68 = a6;
  *a6 = 0;
  bstrString = 0;
  v58 = 0;
  v57 = 0;
  v61 = 0;
  v60 = 0;
  Block = v69;
  if ( a5 == 1 )
  {
    if ( lpWideCharStr )
      v47 = *((_DWORD *)lpWideCharStr - 1);
    else
      v47 = 0;
    v45 = rtExpandString(lpWideCharStr, v47 >> 1, a4, &bstrString, &v60, &v57);
    if ( v45 < 0 )
    {
      v34 = v60;
      goto LABEL_52;
    }
    if ( a2 )
      v48 = *((_DWORD *)a2 - 1);
    else
      v48 = 0;
    v45 = rtExpandString(a2, v48 >> 1, a4, &v58, 0, 0);
    if ( v45 < 0 )
    {
      v34 = v60;
      goto LABEL_51;
    }
    v10 = bstrString;
    a2 = v58;
    a3 = v54;
  }
  else
  {
    v10 = lpWideCharStr;
  }
  v11 = 0;
  rgsabound = (SAFEARRAYBOUND)v10;
  v12 = 0;
  v55 = 0;
  v56 = 0;
  if ( v10 )
    v13 = *((_DWORD *)v10 - 1);
  else
    v13 = 0;
  v14 = v13 >> 1;
  v64 = v14;
  if ( a2 )
    v15 = *((_DWORD *)a2 - 1);
  else
    v15 = 0;
  v16 = v15 >> 1;
  v17 = a3;
  if ( a3 >= 20 )
    v17 = 20;
  v63 = v17;
LABEL_10:
  while ( v11 < a3 && v16 && v14 - v12 >= v16 )
  {
    v18 = *a2;
    v66 = &v10[v12];
    v19 = v66;
    v20 = &v66[v14 - v12 - (unsigned __int64)v16 + 1];
LABEL_14:
    if ( v19 >= v20 )
    {
LABEL_19:
      a3 = v54;
      break;
    }
    for ( i = v20 - v19; ; LODWORD(i) = i - 1 )
    {
      v22 = v19;
      if ( !(_DWORD)i )
        goto LABEL_19;
      ++v19;
      if ( *v22 == v18 )
        break;
    }
    if ( memcmp_0(v22 + 1, a2 + 1, 2 * v16 - 2) )
      goto LABEL_14;
    v34 = v60;
    v35 = v22 - v66;
    v36 = v35 + v55;
    if ( v60 )
    {
      for ( j = v56; j < v57; ++j )
      {
        v50 = *((_DWORD *)v60 + 4 * j + 1);
        if ( v36 == v50 + 1 )
        {
LABEL_91:
          v14 = v64;
          v12 = v36 + 1;
          v10 = (LPCWCH)rgsabound;
          a3 = v54;
          v55 = v36 + 1;
          goto LABEL_10;
        }
        if ( v36 <= v50 )
          break;
      }
    }
    v12 = v35 + v16 + v55;
    v55 = v12;
    v37 = v12 - 1;
    if ( v60 )
    {
      for ( k = v56; k < v57; ++k )
      {
        if ( v37 == *((_DWORD *)v60 + 4 * k + 1) )
          goto LABEL_91;
        if ( v37 < *((_DWORD *)v60 + 4 * k + 1) )
          break;
      }
    }
    if ( v11 < v63 )
      goto LABEL_39;
    v52 = v54;
    if ( v63 + 20 < v54 )
      v52 = v63 + 20;
    v63 = v52;
    if ( (unsigned __int64)v52 > 0x1FFFFFFF )
    {
LABEL_106:
      v9 = v61;
      v45 = -2146828281;
      goto LABEL_51;
    }
    if ( Block != v69 )
    {
      if ( !ResizeMemory(&Block, 8 * v52) )
        goto LABEL_106;
      v12 = v55;
LABEL_39:
      v38 = Block;
      goto LABEL_40;
    }
    v53 = malloc(8LL * v52);
    Block = v53;
    v38 = v53;
    if ( !v53 )
      goto LABEL_106;
    v12 = v55;
    *v53 = v69[0];
    v53[1] = v69[1];
    v53[2] = v69[2];
    v53[3] = v69[3];
    v53[4] = v69[4];
    v53[5] = v69[5];
    v53[6] = v69[6];
    v53[7] = v69[7];
    v53[8] = v69[8];
    v53[9] = v69[9];
LABEL_40:
    v39 = 0;
    if ( v34 )
      v39 = v57;
    v40 = 0;
    if ( v34 )
      v40 = v56;
    for ( m = v40; m < v39; v40 = ++m )
    {
      if ( v36 <= *((_DWORD *)v34 + 4 * m + 1) )
        break;
    }
    v38[2 * v11] = v36 - m;
    v42 = (char *)&v38[2 * v11];
    v43 = 0;
    if ( v34 )
      v43 = v40;
    v56 = v43;
    for ( n = v43; n < v39; v56 = ++n )
    {
      if ( v37 <= *((_DWORD *)v34 + 4 * n + 1) )
        break;
    }
    v14 = v64;
    v10 = (LPCWCH)rgsabound;
    ++v11;
    a3 = v54;
    *((_DWORD *)v42 + 1) = v37 - n;
  }
  v23 = v11 + 1;
  if ( v11 >= a3 )
    v23 = v11;
  v24 = 0;
  rgsabound.cElements = v23;
  rgsabound.lLbound = 0;
  v25 = SafeArrayCreate(0xCu, 1u, &rgsabound);
  v61 = v25;
  v9 = v25;
  if ( v25 )
  {
    pvData = v25->pvData;
    v27 = 0;
    v28 = v67;
    while ( v24 < v23 )
    {
      if ( v24 < v23 - 1 )
      {
        v31 = v24;
        v30 = *((_DWORD *)Block + 2 * v24);
      }
      else
      {
        if ( v28 )
          v29 = *((_DWORD *)v28 - 1);
        else
          v29 = 0;
        v30 = v29 >> 1;
        v31 = v24;
      }
      v32 = v30 - v27;
      v33 = 0;
      if ( (unsigned __int64)(2 * v32) < 0x7FFFFFFD )
        v33 = SysAllocStringLen(&v28[v27], v32);
      pvData[3 * v31 + 1] = v33;
      if ( !v33 )
      {
        v9 = v61;
        v45 = -2146828274;
        goto LABEL_50;
      }
      LOWORD(pvData[3 * v31]) = 8;
      if ( v24 < v23 - 1 )
        v27 = *((_DWORD *)Block + 2 * v31 + 1) + 1;
      ++v24;
    }
    v9 = 0;
    v45 = 0;
    *v68 = v61;
  }
  else
  {
    v45 = -2146828281;
  }
LABEL_50:
  v34 = v60;
LABEL_51:
  v6 = v58;
LABEL_52:
  if ( Block && v69 != Block )
    free(Block);
  if ( v34 )
    free(v34);
  if ( v9 )
    SafeArrayDestroy(v9);
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v6 )
    SysFreeString(v6);
  return (unsigned int)v45;
}

```

## disassembly

```asm
0x1800196f0  mov     r11, rsp
0x1800196f3  push    rbp
0x1800196f4  push    rbx
0x1800196f5  push    r15
0x1800196f7  lea     rbp, [rsp-70h]
0x1800196fc  sub     rsp, 170h
0x180019703  mov     rax, cs:__security_cookie
0x18001970a  xor     rax, rsp
0x18001970d  mov     [rbp+80h+var_50], rax
0x180019711  xor     ebx, ebx
0x180019713  mov     [r11-20h], rsi
0x180019717  cmp     [rbp+80h+arg_20], 1
0x18001971e  mov     rax, rcx
0x180019721  mov     [r11-28h], rdi
0x180019725  mov     r15d, ebx
0x180019728  mov     [r11-30h], r12
0x18001972c  mov     edi, r9d
0x18001972f  mov     r12, rdx
0x180019732  mov     [rbp+80h+var_100], rcx
0x180019736  mov     rdx, [rbp+80h+arg_28]
0x18001973d  lea     rcx, [rbp+80h+var_F0]
0x180019741  mov     [r11-40h], r14
0x180019745  mov     esi, ebx
0x180019747  mov     [rsp+180h+var_150], r8d
0x18001974c  mov     [rbp+80h+var_F8], rdx
0x180019750  mov     [rdx], rbx
0x180019753  mov     [rsp+180h+bstrString], rbx
0x180019758  mov     [rsp+180h+var_140], rbx
0x18001975d  mov     [rsp+180h+var_144], ebx
0x180019761  mov     [rsp+180h+var_128], rbx
0x180019766  mov     [rsp+180h+var_130], rbx
0x18001976b  mov     [rsp+180h+Block], rcx
0x180019770  jz      loc_180019ACC
0x180019776  mov     rdx, rax
0x180019779  mov     [rsp+180h+var_30], r13
0x180019781  mov     r13d, ebx
0x180019784  mov     qword ptr [rsp+180h+rgsabound.cElements], rdx
0x180019789  mov     r10d, ebx
0x18001978c  mov     [rsp+180h+var_14C], ebx
0x180019790  mov     [rsp+180h+var_148], ebx
0x180019794  test    rdx, rdx
0x180019797  jz      loc_180019AA6
0x18001979d  mov     eax, [rdx-4]
0x1800197a0  shr     eax, 1
0x1800197a2  mov     [rsp+180h+var_114], eax
0x1800197a6  test    r12, r12
0x1800197a9  jz      loc_180019AAD
0x1800197af  mov     r15d, [r12-4]
0x1800197b4  mov     ecx, 14h
0x1800197b9  shr     r15d, 1
0x1800197bc  cmp     r8d, ecx
0x1800197bf  mov     esi, r8d
0x1800197c2  cmovge  esi, ecx
0x1800197c5  mov     [rsp+180h+var_118], esi
0x1800197c9  cmp     r13d, r8d
0x1800197cc  jge     short loc_180019834
0x1800197ce  test    r15d, r15d
0x1800197d1  jz      short loc_180019834
0x1800197d3  mov     ecx, eax
0x1800197d5  sub     ecx, r10d
0x1800197d8  cmp     ecx, r15d
0x1800197db  jb      short loc_180019834
0x1800197dd  movzx   esi, word ptr [r12]
0x1800197e2  mov     eax, r10d
0x1800197e5  mov     r14d, ecx
0x1800197e8  lea     rdx, [rdx+rax*2]
0x1800197ec  mov     eax, r15d
0x1800197ef  sub     r14, rax
0x1800197f2  mov     [rsp+180h+var_108], rdx
0x1800197f7  inc     r14
0x1800197fa  mov     rdi, rdx
0x1800197fd  lea     r14, [rdx+r14*2]
0x180019801  lea     ecx, ds:0FFFFFFFFFFFFFFFEh[r15*2]
0x180019809  cmp     rdi, r14
0x18001980c  jnb     short loc_18001982F
0x18001980e  mov     rax, r14
0x180019811  sub     rax, rdi
0x180019814  sar     rax, 1
0x180019817  mov     rbx, rdi
0x18001981a  test    eax, eax
0x18001981c  jz      short loc_18001982F
0x18001981e  lea     rdi, [rbx+2]
0x180019822  cmp     [rbx], si
0x180019825  jz      loc_180019913
0x18001982b  dec     eax
0x18001982d  jmp     short loc_180019817
0x18001982f  mov     r8d, [rsp+180h+var_150]
0x180019834  cmp     r13d, r8d
0x180019837  lea     edi, [r13+1]
0x18001983b  mov     ecx, 0Ch; vt
0x180019840  lea     r8, [rsp+180h+rgsabound]; rgsabound
0x180019845  cmovge  edi, r13d
0x180019849  mov     edx, 1; cDims
0x18001984e  xor     ebx, ebx
0x180019850  mov     [rsp+180h+rgsabound.cElements], edi
0x180019854  mov     [rsp+180h+rgsabound.lLbound], ebx
0x180019858  call    cs:__imp_SafeArrayCreate
0x18001985f  nop     dword ptr [rax+rax+00h]
0x180019864  mov     [rsp+180h+var_128], rax
0x180019869  mov     rsi, rax
0x18001986c  test    rax, rax
0x18001986f  jz      loc_1800199E0
0x180019875  mov     r12, [rax+10h]
0x180019879  mov     r14d, ebx
0x18001987c  mov     r13, [rbp+80h+var_100]
0x180019880  mov     r9d, 8
0x180019886  cmp     ebx, edi
0x180019888  jge     loc_180019A91
0x18001988e  lea     r15d, [rdi-1]
0x180019892  cmp     ebx, r15d
0x180019895  jl      loc_180019ABC
0x18001989b  test    r13, r13
0x18001989e  jz      loc_180019AB5
0x1800198a4  mov     eax, [r13-4]
0x1800198a8  shr     eax, 1
0x1800198aa  movsxd  rsi, ebx
0x1800198ad  sub     eax, r14d
0x1800198b0  xor     r8d, r8d
0x1800198b3  mov     edx, eax; ui
0x1800198b5  add     rax, rax
0x1800198b8  cmp     rax, 7FFFFFFDh
0x1800198be  jnb     short loc_1800198E3
0x1800198c0  mov     eax, r14d
0x1800198c3  lea     rcx, ds:0[rax*2]
0x1800198cb  add     rcx, r13; strIn
0x1800198ce  call    cs:__imp_SysAllocStringLen
0x1800198d5  nop     dword ptr [rax+rax+00h]
0x1800198da  mov     r8, rax
0x1800198dd  mov     r9d, 8
0x1800198e3  lea     rcx, [rsi+rsi*2]
0x1800198e7  mov     [r12+rcx*8+8], r8
0x1800198ec  test    r8, r8
0x1800198ef  jz      loc_180019A65
0x1800198f5  mov     [r12+rcx*8], r9w
0x1800198fa  cmp     ebx, r15d
0x1800198fd  jge     short loc_18001990C
0x1800198ff  mov     rax, [rsp+180h+Block]
0x180019904  mov     r14d, [rax+rsi*8+4]
0x180019909  inc     r14d
0x18001990c  inc     ebx
0x18001990e  jmp     loc_180019886
0x180019913  mov     r8d, ecx; Size
0x180019916  lea     rdx, [r12+2]; Buf2
0x18001991b  mov     rcx, rdi; Buf1
0x18001991e  call    memcmp_0
0x180019923  test    eax, eax
0x180019925  jnz     loc_180019801
0x18001992b  sub     rbx, [rsp+180h+var_108]
0x180019930  mov     r10d, [rsp+180h+var_14C]
0x180019935  mov     r14, [rsp+180h+var_130]
0x18001993a  mov     r8d, [rsp+180h+var_148]
0x18001993f  mov     r9d, [rsp+180h+var_144]
0x180019944  sar     rbx, 1
0x180019947  lea     edi, [rbx+r10]
0x18001994b  test    r14, r14
0x18001994e  jnz     loc_180019B48
0x180019954  lea     eax, [rbx+r15]
0x180019958  add     r10d, eax
0x18001995b  mov     [rsp+180h+var_14C], r10d
0x180019960  lea     ebx, [r10-1]
0x180019964  test    r14, r14
0x180019967  jnz     loc_180019B90
0x18001996d  mov     esi, [rsp+180h+var_118]
0x180019971  cmp     r13d, esi
0x180019974  jge     loc_180019BCE
0x18001997a  mov     r9, [rsp+180h+Block]
0x18001997f  xor     r8d, r8d
0x180019982  test    r14, r14
0x180019985  cmovnz  r8d, [rsp+180h+var_144]
0x18001998b  xor     ecx, ecx
0x18001998d  test    r14, r14
0x180019990  cmovnz  ecx, [rsp+180h+var_148]
0x180019995  mov     edx, ecx
0x180019997  cmp     ecx, r8d
0x18001999a  jb      loc_180019CA0
0x1800199a0  sub     edi, edx
0x1800199a2  movsxd  rax, r13d
0x1800199a5  mov     [r9+rax*8], edi
0x1800199a9  lea     r9, [r9+rax*8]
0x1800199ad  xor     edi, edi
0x1800199af  test    r14, r14
0x1800199b2  cmovnz  edi, ecx
0x1800199b5  mov     [rsp+180h+var_148], edi
0x1800199b9  mov     ecx, edi
0x1800199bb  cmp     edi, r8d
0x1800199be  jb      loc_180019CBE
0x1800199c4  mov     eax, [rsp+180h+var_114]
0x1800199c8  sub     ebx, ecx
0x1800199ca  mov     rdx, qword ptr [rsp+180h+rgsabound.cElements]
0x1800199cf  inc     r13d
0x1800199d2  mov     r8d, [rsp+180h+var_150]
0x1800199d7  mov     [r9+4], ebx
0x1800199db  jmp     loc_1800197C9
0x1800199e0  mov     ebx, 800A0007h
0x1800199e5  mov     r14, [rsp+180h+var_130]
0x1800199ea  mov     r13, [rsp+180h+var_30]
0x1800199f2  mov     r15, [rsp+180h+var_140]
0x1800199f7  mov     rdi, [rsp+180h+Block]
0x1800199fc  mov     r12, [rsp+180h+var_28]
0x180019a04  test    rdi, rdi
0x180019a07  jnz     short loc_180019A74
0x180019a09  mov     rdi, [rsp+180h+var_20]
0x180019a11  test    r14, r14
0x180019a14  jnz     loc_180019CED
0x180019a1a  mov     r14, [rsp+180h+var_38]
0x180019a22  test    rsi, rsi
0x180019a25  jnz     loc_180019D01
0x180019a2b  mov     rax, [rsp+180h+bstrString]
0x180019a30  mov     rsi, [rsp+180h+var_18]
0x180019a38  test    rax, rax
0x180019a3b  jnz     loc_180019D15
0x180019a41  test    r15, r15
0x180019a44  jnz     loc_180019D29
0x180019a4a  mov     eax, ebx
0x180019a4c  mov     rcx, [rbp+80h+var_50]
0x180019a50  xor     rcx, rsp; StackCookie
0x180019a53  call    __security_check_cookie
0x180019a58  add     rsp, 170h
0x180019a5f  pop     r15
0x180019a61  pop     rbx
0x180019a62  pop     rbp
0x180019a63  retn
0x180019a65  mov     rsi, [rsp+180h+var_128]
0x180019a6a  mov     ebx, 800A000Eh
0x180019a6f  jmp     loc_1800199E5
0x180019a74  lea     rax, [rbp+80h+var_F0]
0x180019a78  cmp     rax, rdi
0x180019a7b  jz      short loc_180019A09
0x180019a7d  mov     rcx, rdi; Block
0x180019a80  call    cs:__imp_free
0x180019a87  nop     dword ptr [rax+rax+00h]
0x180019a8c  jmp     loc_180019A09
0x180019a91  mov     rcx, [rbp+80h+var_F8]
0x180019a95  xor     esi, esi
0x180019a97  mov     rax, [rsp+180h+var_128]
0x180019a9c  xor     ebx, ebx
0x180019a9e  mov     [rcx], rax
0x180019aa1  jmp     loc_1800199E5
0x180019aa6  mov     eax, ebx
0x180019aa8  jmp     loc_1800197A0
0x180019aad  mov     r15d, ebx
0x180019ab0  jmp     loc_1800197B4
0x180019ab5  xor     eax, eax
0x180019ab7  jmp     loc_1800198A8
0x180019abc  mov     rax, [rsp+180h+Block]
0x180019ac1  movsxd  rsi, ebx
0x180019ac4  mov     eax, [rax+rsi*8]
0x180019ac7  jmp     loc_1800198AD
0x180019acc  test    rax, rax
0x180019acf  jz      loc_180019B7B
0x180019ad5  mov     edx, [rax-4]
0x180019ad8  lea     rcx, [rsp+180h+var_144]
0x180019add  shr     edx, 1; cchWideChar
0x180019adf  mov     [rsp+180h+var_158], rcx; unsigned int *
0x180019ae4  lea     r9, [rsp+180h+bstrString]; unsigned __int16 **
0x180019ae9  lea     rcx, [rsp+180h+var_130]
0x180019aee  mov     r8d, edi; Locale
0x180019af1  mov     [rsp+180h+var_160], rcx; struct ExpPosition **
0x180019af6  mov     rcx, rax; lpWideCharStr
0x180019af9  call    ?rtExpandString@@YAJPEBGIKPEAPEAGPEAPEAUExpPosition@@PEAI@Z; rtExpandString(ushort const *,uint,ulong,ushort * *,ExpPosition * *,uint *)
0x180019afe  mov     ebx, eax
0x180019b00  test    eax, eax
0x180019b02  js      short loc_180019B71
0x180019b04  xor     eax, eax
0x180019b06  test    r12, r12
0x180019b09  jz      short loc_180019B82
0x180019b0b  mov     edx, [r12-4]
0x180019b10  mov     [rsp+180h+var_158], rax; unsigned int *
0x180019b15  lea     r9, [rsp+180h+var_140]; unsigned __int16 **
0x180019b1a  shr     edx, 1; cchWideChar
0x180019b1c  mov     r8d, edi; Locale
0x180019b1f  mov     rcx, r12; lpWideCharStr
0x180019b22  mov     [rsp+180h+var_160], rax; struct ExpPosition **
0x180019b27  call    ?rtExpandString@@YAJPEBGIKPEAPEAGPEAPEAUExpPosition@@PEAI@Z; rtExpandString(ushort const *,uint,ulong,ushort * *,ExpPosition * *,uint *)
0x180019b2c  mov     ebx, eax
0x180019b2e  test    eax, eax
0x180019b30  js      short loc_180019B86
0x180019b32  mov     rdx, [rsp+180h+bstrString]
0x180019b37  xor     ebx, ebx
0x180019b39  mov     r12, [rsp+180h+var_140]
0x180019b3e  mov     r8d, [rsp+180h+var_150]
0x180019b43  jmp     loc_180019779
0x180019b48  mov     ecx, r8d
0x180019b4b  cmp     ecx, r9d
0x180019b4e  jnb     loc_180019954
0x180019b54  mov     eax, ecx
0x180019b56  add     rax, rax
0x180019b59  mov     edx, [r14+rax*8+4]
0x180019b5e  lea     eax, [rdx+1]
0x180019b61  cmp     edi, eax
0x180019b63  jz      short loc_180019BB2
0x180019b65  cmp     edi, edx
0x180019b67  jbe     loc_180019954
0x180019b6d  inc     ecx
0x180019b6f  jmp     short loc_180019B4B
0x180019b71  mov     r14, [rsp+180h+var_130]
0x180019b76  jmp     loc_1800199F7
0x180019b7b  mov     edx, ebx
0x180019b7d  jmp     loc_180019AD8
0x180019b82  mov     edx, eax
  ... truncated ...
```
