# rtStandardSplit

- ea: `0x18001f420`
- end: `0x18001fa35`
- name: `rtStandardSplit`
- size: `1557`
- prototype: `__int64 __fastcall(const OLECHAR *lpWideCharStr, BSTR, int, LCID, int, SAFEARRAY **)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18001d9f0`
- `0x18001f348`

## callees

- `0x18001f420`
- `0x180030758`
- `0x180060044`
- `0x180076722`
- `0x1800767a0`

## import_xrefs

- `msvcrt!malloc` at `0x18001f91b`
- `msvcrt!malloc` at `0x18001f91b`
- `msvcrt!free` at `0x18001f7a3`
- `msvcrt!free` at `0x18001fa00`
- `msvcrt!free` at `0x18001f7a3`
- `msvcrt!free` at `0x18001fa00`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001f5f8`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001f5f8`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fa1c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fa2a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fa1c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fa2a`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18001f588`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18001f588`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001fa0e`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001fa0e`

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
0x18001f420  mov     r11, rsp
0x18001f423  push    rbp
0x18001f424  push    rbx
0x18001f425  push    r15
0x18001f427  lea     rbp, [rsp-70h]
0x18001f42c  sub     rsp, 170h
0x18001f433  mov     rax, cs:__security_cookie
0x18001f43a  xor     rax, rsp
0x18001f43d  mov     [rbp+80h+var_50], rax
0x18001f441  xor     ebx, ebx
0x18001f443  mov     [r11-20h], rsi
0x18001f447  cmp     [rbp+80h+arg_20], 1
0x18001f44e  mov     rax, rcx
0x18001f451  mov     [r11-28h], rdi
0x18001f455  mov     r15d, ebx
0x18001f458  mov     [r11-30h], r12
0x18001f45c  mov     edi, r9d
0x18001f45f  mov     r12, rdx
0x18001f462  mov     [rbp+80h+var_100], rcx
0x18001f466  mov     rdx, [rbp+80h+arg_28]
0x18001f46d  lea     rcx, [rbp+80h+var_F0]
0x18001f471  mov     [r11-40h], r14
0x18001f475  mov     esi, ebx
0x18001f477  mov     [rsp+180h+var_150], r8d
0x18001f47c  mov     [rbp+80h+var_F8], rdx
0x18001f480  mov     [rdx], rbx
0x18001f483  mov     [rsp+180h+bstrString], rbx
0x18001f488  mov     [rsp+180h+var_140], rbx
0x18001f48d  mov     [rsp+180h+var_144], ebx
0x18001f491  mov     [rsp+180h+var_128], rbx
0x18001f496  mov     [rsp+180h+var_130], rbx
0x18001f49b  mov     [rsp+180h+Block], rcx
0x18001f4a0  jz      loc_18001F7E6
0x18001f4a6  mov     rdx, rax
0x18001f4a9  mov     [rsp+180h+var_30], r13
0x18001f4b1  mov     r13d, ebx
0x18001f4b4  mov     qword ptr [rsp+180h+rgsabound.cElements], rdx
0x18001f4b9  mov     r10d, ebx
0x18001f4bc  mov     [rsp+180h+var_14C], ebx
0x18001f4c0  mov     [rsp+180h+var_148], ebx
0x18001f4c4  test    rdx, rdx
0x18001f4c7  jz      loc_18001F7C0
0x18001f4cd  mov     eax, [rdx-4]
0x18001f4d0  shr     eax, 1
0x18001f4d2  mov     [rsp+180h+var_114], eax
0x18001f4d6  test    r12, r12
0x18001f4d9  jz      loc_18001F7C7
0x18001f4df  mov     r15d, [r12-4]
0x18001f4e4  mov     ecx, 14h
0x18001f4e9  shr     r15d, 1
0x18001f4ec  cmp     r8d, ecx
0x18001f4ef  mov     esi, r8d
0x18001f4f2  cmovge  esi, ecx
0x18001f4f5  mov     [rsp+180h+var_118], esi
0x18001f4f9  cmp     r13d, r8d
0x18001f4fc  jge     short loc_18001F564
0x18001f4fe  test    r15d, r15d
0x18001f501  jz      short loc_18001F564
0x18001f503  mov     ecx, eax
0x18001f505  sub     ecx, r10d
0x18001f508  cmp     ecx, r15d
0x18001f50b  jb      short loc_18001F564
0x18001f50d  movzx   esi, word ptr [r12]
0x18001f512  mov     eax, r10d
0x18001f515  mov     r14d, ecx
0x18001f518  lea     rdx, [rdx+rax*2]
0x18001f51c  mov     eax, r15d
0x18001f51f  sub     r14, rax
0x18001f522  mov     [rsp+180h+var_108], rdx
0x18001f527  inc     r14
0x18001f52a  mov     rdi, rdx
0x18001f52d  lea     r14, [rdx+r14*2]
0x18001f531  lea     ecx, ds:0FFFFFFFFFFFFFFFEh[r15*2]
0x18001f539  cmp     rdi, r14
0x18001f53c  jnb     short loc_18001F55F
0x18001f53e  mov     rax, r14
0x18001f541  sub     rax, rdi
0x18001f544  sar     rax, 1
0x18001f547  mov     rbx, rdi
0x18001f54a  test    eax, eax
0x18001f54c  jz      short loc_18001F55F
0x18001f54e  lea     rdi, [rbx+2]
0x18001f552  cmp     [rbx], si
0x18001f555  jz      loc_18001F637
0x18001f55b  dec     eax
0x18001f55d  jmp     short loc_18001F547
0x18001f55f  mov     r8d, [rsp+180h+var_150]
0x18001f564  cmp     r13d, r8d
0x18001f567  lea     edi, [r13+1]
0x18001f56b  mov     ecx, 0Ch; vt
0x18001f570  lea     r8, [rsp+180h+rgsabound]; rgsabound
0x18001f575  cmovge  edi, r13d
0x18001f579  mov     edx, 1; cDims
0x18001f57e  xor     ebx, ebx
0x18001f580  mov     [rsp+180h+rgsabound.cElements], edi
0x18001f584  mov     [rsp+180h+rgsabound.lLbound], ebx
0x18001f588  call    cs:__imp_SafeArrayCreate
0x18001f58e  mov     [rsp+180h+var_128], rax
0x18001f593  mov     rsi, rax
0x18001f596  test    rax, rax
0x18001f599  jz      loc_18001F704
0x18001f59f  mov     r12, [rax+10h]
0x18001f5a3  mov     r14d, ebx
0x18001f5a6  mov     r13, [rbp+80h+var_100]
0x18001f5aa  mov     r9d, 8
0x18001f5b0  cmp     ebx, edi
0x18001f5b2  jge     loc_18001F7AB
0x18001f5b8  lea     r15d, [rdi-1]
0x18001f5bc  cmp     ebx, r15d
0x18001f5bf  jl      loc_18001F7D6
0x18001f5c5  test    r13, r13
0x18001f5c8  jz      loc_18001F7CF
0x18001f5ce  mov     eax, [r13-4]
0x18001f5d2  shr     eax, 1
0x18001f5d4  movsxd  rsi, ebx
0x18001f5d7  sub     eax, r14d
0x18001f5da  xor     r8d, r8d
0x18001f5dd  mov     edx, eax; ui
0x18001f5df  add     rax, rax
0x18001f5e2  cmp     rax, 7FFFFFFDh
0x18001f5e8  jnb     short loc_18001F607
0x18001f5ea  mov     eax, r14d
0x18001f5ed  lea     rcx, ds:0[rax*2]
0x18001f5f5  add     rcx, r13; strIn
0x18001f5f8  call    cs:__imp_SysAllocStringLen
0x18001f5fe  mov     r8, rax
0x18001f601  mov     r9d, 8
0x18001f607  lea     rcx, [rsi+rsi*2]
0x18001f60b  mov     [r12+rcx*8+8], r8
0x18001f610  test    r8, r8
0x18001f613  jz      loc_18001F788
0x18001f619  mov     [r12+rcx*8], r9w
0x18001f61e  cmp     ebx, r15d
0x18001f621  jge     short loc_18001F630
0x18001f623  mov     rax, [rsp+180h+Block]
0x18001f628  mov     r14d, [rax+rsi*8+4]
0x18001f62d  inc     r14d
0x18001f630  inc     ebx
0x18001f632  jmp     loc_18001F5B0
0x18001f637  mov     r8d, ecx; Size
0x18001f63a  lea     rdx, [r12+2]; Buf2
0x18001f63f  mov     rcx, rdi; Buf1
0x18001f642  call    memcmp_0
0x18001f647  test    eax, eax
0x18001f649  jnz     loc_18001F531
0x18001f64f  sub     rbx, [rsp+180h+var_108]
0x18001f654  mov     r10d, [rsp+180h+var_14C]
0x18001f659  mov     r14, [rsp+180h+var_130]
0x18001f65e  mov     r8d, [rsp+180h+var_148]
0x18001f663  mov     r9d, [rsp+180h+var_144]
0x18001f668  sar     rbx, 1
0x18001f66b  lea     edi, [rbx+r10]
0x18001f66f  test    r14, r14
0x18001f672  jnz     loc_18001F862
0x18001f678  lea     eax, [rbx+r15]
0x18001f67c  add     r10d, eax
0x18001f67f  mov     [rsp+180h+var_14C], r10d
0x18001f684  lea     ebx, [r10-1]
0x18001f688  test    r14, r14
0x18001f68b  jnz     loc_18001F8AA
0x18001f691  mov     esi, [rsp+180h+var_118]
0x18001f695  cmp     r13d, esi
0x18001f698  jge     loc_18001F8E8
0x18001f69e  mov     r9, [rsp+180h+Block]
0x18001f6a3  xor     r8d, r8d
0x18001f6a6  test    r14, r14
0x18001f6a9  cmovnz  r8d, [rsp+180h+var_144]
0x18001f6af  xor     ecx, ecx
0x18001f6b1  test    r14, r14
0x18001f6b4  cmovnz  ecx, [rsp+180h+var_148]
0x18001f6b9  mov     edx, ecx
0x18001f6bb  cmp     ecx, r8d
0x18001f6be  jb      loc_18001F9B0
0x18001f6c4  sub     edi, edx
0x18001f6c6  movsxd  rax, r13d
0x18001f6c9  mov     [r9+rax*8], edi
0x18001f6cd  lea     r9, [r9+rax*8]
0x18001f6d1  xor     edi, edi
0x18001f6d3  test    r14, r14
0x18001f6d6  cmovnz  edi, ecx
0x18001f6d9  mov     [rsp+180h+var_148], edi
0x18001f6dd  mov     ecx, edi
0x18001f6df  cmp     edi, r8d
0x18001f6e2  jb      loc_18001F9CE
0x18001f6e8  mov     eax, [rsp+180h+var_114]
0x18001f6ec  sub     ebx, ecx
0x18001f6ee  mov     rdx, qword ptr [rsp+180h+rgsabound.cElements]
0x18001f6f3  inc     r13d
0x18001f6f6  mov     r8d, [rsp+180h+var_150]
0x18001f6fb  mov     [r9+4], ebx
0x18001f6ff  jmp     loc_18001F4F9
0x18001f704  mov     ebx, 800A0007h
0x18001f709  mov     r14, [rsp+180h+var_130]
0x18001f70e  mov     r13, [rsp+180h+var_30]
0x18001f716  mov     r15, [rsp+180h+var_140]
0x18001f71b  mov     rdi, [rsp+180h+Block]
0x18001f720  mov     r12, [rsp+180h+var_28]
0x18001f728  test    rdi, rdi
0x18001f72b  jnz     short loc_18001F797
0x18001f72d  mov     rdi, [rsp+180h+var_20]
0x18001f735  test    r14, r14
0x18001f738  jnz     loc_18001F9FD
0x18001f73e  mov     r14, [rsp+180h+var_38]
0x18001f746  test    rsi, rsi
0x18001f749  jnz     loc_18001FA0B
0x18001f74f  mov     rax, [rsp+180h+bstrString]
0x18001f754  mov     rsi, [rsp+180h+var_18]
0x18001f75c  test    rax, rax
0x18001f75f  jnz     loc_18001FA19
0x18001f765  test    r15, r15
0x18001f768  jnz     loc_18001FA27
0x18001f76e  mov     eax, ebx
0x18001f770  mov     rcx, [rbp+80h+var_50]
0x18001f774  xor     rcx, rsp; StackCookie
0x18001f777  call    __security_check_cookie
0x18001f77c  add     rsp, 170h
0x18001f783  pop     r15
0x18001f785  pop     rbx
0x18001f786  pop     rbp
0x18001f787  retn
0x18001f788  mov     rsi, [rsp+180h+var_128]
0x18001f78d  mov     ebx, 800A000Eh
0x18001f792  jmp     loc_18001F709
0x18001f797  lea     rax, [rbp+80h+var_F0]
0x18001f79b  cmp     rax, rdi
0x18001f79e  jz      short loc_18001F72D
0x18001f7a0  mov     rcx, rdi; Block
0x18001f7a3  call    cs:__imp_free
0x18001f7a9  jmp     short loc_18001F72D
0x18001f7ab  mov     rcx, [rbp+80h+var_F8]
0x18001f7af  xor     esi, esi
0x18001f7b1  mov     rax, [rsp+180h+var_128]
0x18001f7b6  xor     ebx, ebx
0x18001f7b8  mov     [rcx], rax
0x18001f7bb  jmp     loc_18001F709
0x18001f7c0  mov     eax, ebx
0x18001f7c2  jmp     loc_18001F4D0
0x18001f7c7  mov     r15d, ebx
0x18001f7ca  jmp     loc_18001F4E4
0x18001f7cf  xor     eax, eax
0x18001f7d1  jmp     loc_18001F5D2
0x18001f7d6  mov     rax, [rsp+180h+Block]
0x18001f7db  movsxd  rsi, ebx
0x18001f7de  mov     eax, [rax+rsi*8]
0x18001f7e1  jmp     loc_18001F5D7
0x18001f7e6  test    rax, rax
0x18001f7e9  jz      loc_18001F895
0x18001f7ef  mov     edx, [rax-4]
0x18001f7f2  lea     rcx, [rsp+180h+var_144]
0x18001f7f7  shr     edx, 1; cchWideChar
0x18001f7f9  mov     [rsp+180h+var_158], rcx; unsigned int *
0x18001f7fe  lea     r9, [rsp+180h+bstrString]; unsigned __int16 **
0x18001f803  lea     rcx, [rsp+180h+var_130]
0x18001f808  mov     r8d, edi; Locale
0x18001f80b  mov     [rsp+180h+var_160], rcx; struct ExpPosition **
0x18001f810  mov     rcx, rax; lpWideCharStr
0x18001f813  call    ?rtExpandString@@YAJPEBGIKPEAPEAGPEAPEAUExpPosition@@PEAI@Z; rtExpandString(ushort const *,uint,ulong,ushort * *,ExpPosition * *,uint *)
0x18001f818  mov     ebx, eax
0x18001f81a  test    eax, eax
0x18001f81c  js      short loc_18001F88B
0x18001f81e  xor     eax, eax
0x18001f820  test    r12, r12
0x18001f823  jz      short loc_18001F89C
0x18001f825  mov     edx, [r12-4]
0x18001f82a  mov     [rsp+180h+var_158], rax; unsigned int *
0x18001f82f  lea     r9, [rsp+180h+var_140]; unsigned __int16 **
0x18001f834  shr     edx, 1; cchWideChar
0x18001f836  mov     r8d, edi; Locale
0x18001f839  mov     rcx, r12; lpWideCharStr
0x18001f83c  mov     [rsp+180h+var_160], rax; struct ExpPosition **
0x18001f841  call    ?rtExpandString@@YAJPEBGIKPEAPEAGPEAPEAUExpPosition@@PEAI@Z; rtExpandString(ushort const *,uint,ulong,ushort * *,ExpPosition * *,uint *)
0x18001f846  mov     ebx, eax
0x18001f848  test    eax, eax
0x18001f84a  js      short loc_18001F8A0
0x18001f84c  mov     rdx, [rsp+180h+bstrString]
0x18001f851  xor     ebx, ebx
0x18001f853  mov     r12, [rsp+180h+var_140]
0x18001f858  mov     r8d, [rsp+180h+var_150]
0x18001f85d  jmp     loc_18001F4A9
0x18001f862  mov     ecx, r8d
0x18001f865  cmp     ecx, r9d
0x18001f868  jnb     loc_18001F678
0x18001f86e  mov     eax, ecx
0x18001f870  add     rax, rax
0x18001f873  mov     edx, [r14+rax*8+4]
0x18001f878  lea     eax, [rdx+1]
0x18001f87b  cmp     edi, eax
0x18001f87d  jz      short loc_18001F8CC
0x18001f87f  cmp     edi, edx
0x18001f881  jbe     loc_18001F678
0x18001f887  inc     ecx
0x18001f889  jmp     short loc_18001F865
0x18001f88b  mov     r14, [rsp+180h+var_130]
0x18001f890  jmp     loc_18001F71B
0x18001f895  mov     edx, ebx
0x18001f897  jmp     loc_18001F7F2
0x18001f89c  mov     edx, eax
0x18001f89e  jmp     short loc_18001F82A
0x18001f8a0  mov     r14, [rsp+180h+var_130]
0x18001f8a5  jmp     loc_18001F716
  ... truncated ...
```
