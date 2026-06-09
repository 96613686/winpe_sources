# HrAddDirectoryToPath(CUString &,ushort const *)

- ea: `0x180013544`
- end: `0x180013867`
- name: `?HrAddDirectoryToPath@@YAJAEAVCUString@@PEBG@Z`
- size: `803`
- prototype: `int(struct CUString *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x18001b890`
- `0x18001e790`
- `0x180020544`

## callees

- `0x18001347c`
- `0x180013544`
- `0x180013b24`
- `0x180038324`
- `0x180038ce4`
- `0x180043124`
- `0x18004317c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800135e1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800136c9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013705`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001372c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013792`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800137ea`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013810`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800135e1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800136c9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013705`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001372c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013792`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800137ea`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180013810`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800135a1`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180013652`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800135a1`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180013652`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180013751`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180013751`

## pseudocode

```c
__int64 __fastcall HrAddDirectoryToPath(void **a1, const unsigned __int16 *a2)
{
  __int64 v2; // r12
  WCHAR *v3; // rbx
  const wchar_t *v5; // rsi
  __int64 v6; // rax
  size_t v7; // r15
  const wchar_t *v8; // rcx
  size_t v9; // r8
  wchar_t *v10; // r14
  HRESULT v11; // eax
  size_t v12; // rdx
  size_t *v13; // r8
  wchar_t v14; // r11
  HRESULT v15; // edi
  HRESULT v16; // esi
  STRSAFE_PCNZWCH v17; // rcx
  __int64 v18; // rax
  size_t v19; // r14
  wchar_t *v20; // rax
  const wchar_t *v21; // rcx
  size_t v22; // r8
  size_t v23; // r9
  wchar_t *v24; // r15
  size_t v25; // rdx
  size_t *v26; // r8
  HRESULT v27; // esi
  size_t *v28; // r8
  bool v29; // zf
  int Win32Error; // eax
  size_t v32; // [rsp+20h] [rbp-20h]
  STRSAFE_PCNZWCH pszSrc[2]; // [rsp+30h] [rbp-10h] BYREF
  size_t pcchDestLength; // [rsp+90h] [rbp+50h] BYREF

  v2 = -1;
  v3 = 0;
  pszSrc[0] = 0;
  if ( a1 == (void **)pszSrc )
  {
LABEL_12:
    v15 = HrEnsurePathBackslash((struct CUString *)pszSrc);
    if ( v15 < 0 )
      goto LABEL_39;
    v3 = (WCHAR *)pszSrc[0];
    if ( !a2 )
    {
LABEL_35:
      if ( !CreateDirectoryW(v3, 0) )
      {
        Win32Error = HrFromLastWin32Error();
        v15 = Win32Error;
        if ( Win32Error != -2147024713 && Win32Error < 0 )
          goto LABEL_40;
      }
      v15 = HrEnsurePathBackslash((struct CUString *)pszSrc);
      if ( v15 >= 0 )
      {
        free(*a1);
        *a1 = (void *)pszSrc[0];
        v3 = 0;
        goto LABEL_40;
      }
LABEL_39:
      v3 = (WCHAR *)pszSrc[0];
LABEL_40:
      v17 = WPP_GLOBAL_Control;
      v29 = v15 == 0;
LABEL_33:
      if ( v29 )
        goto LABEL_34;
      goto LABEL_54;
    }
    if ( pszSrc[0] )
    {
      v18 = -1;
      do
        ++v18;
      while ( pszSrc[0][v18] );
    }
    else
    {
      v18 = 0;
    }
    do
      ++v2;
    while ( a2[v2] );
    v19 = v2 + v18 + 1;
    v20 = (wchar_t *)malloc(2 * v19);
    v24 = v20;
    if ( !v20 )
    {
      v15 = -2147024882;
LABEL_27:
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      {
LABEL_32:
        v29 = v15 == 0;
        if ( v15 < 0 )
          goto LABEL_33;
        goto LABEL_35;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids,
        (unsigned int)v15);
LABEL_31:
      v17 = WPP_GLOBAL_Control;
      goto LABEL_32;
    }
    *v20 = 0;
    if ( !v3 )
      goto LABEL_23;
    v15 = StringValidateDestW(v21, v19, v22);
    if ( v15 < 0 )
    {
      if ( v19 )
        goto LABEL_26;
    }
    else
    {
      v15 = StringCopyWorkerW(v24, v25, v26, v3, v32);
    }
    if ( v15 >= 0 )
    {
LABEL_23:
      pcchDestLength = 0;
      v27 = StringValidateDestAndLengthW(v24, v19, &pcchDestLength, v23);
      if ( v27 >= 0 )
        v27 = StringCopyWorkerW(&v24[pcchDestLength], v19 - pcchDestLength, v28, a2, v32);
      v15 = v27;
      if ( v27 >= 0 )
      {
        free(v3);
        v3 = v24;
        pszSrc[0] = v24;
        if ( !v27 )
          goto LABEL_31;
        goto LABEL_27;
      }
    }
LABEL_26:
    free(v24);
    goto LABEL_27;
  }
  v5 = (const wchar_t *)*a1;
  if ( !*a1 )
  {
    free(0);
    goto LABEL_12;
  }
  v6 = -1;
  do
    ++v6;
  while ( v5[v6] );
  v7 = v6 + 1;
  v10 = (wchar_t *)malloc(2 * (v6 + 1));
  if ( !v10 )
  {
    v15 = -2147024882;
    goto LABEL_43;
  }
  v11 = StringValidateDestW(v8, v7, v9);
  v15 = v11;
  if ( v11 < 0 )
  {
    v16 = v11;
    if ( v7 )
    {
      *v10 = v14;
      goto LABEL_50;
    }
  }
  else
  {
    v16 = StringCopyWorkerW(v10, v12, v13, v5, v32);
  }
  v15 = v16;
  if ( v16 < 0 )
  {
LABEL_50:
    free(v10);
    goto LABEL_43;
  }
  free(0);
  v3 = v10;
  pszSrc[0] = v10;
  if ( !v16 )
  {
LABEL_10:
    v17 = WPP_GLOBAL_Control;
    goto LABEL_11;
  }
LABEL_43:
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids,
      (unsigned int)v15);
    goto LABEL_10;
  }
LABEL_11:
  if ( v15 >= 0 )
    goto LABEL_12;
LABEL_54:
  if ( v17 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v17[14] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)v17 + 2), 22, WPP_cd0457ca62d634003859bdcf9006b616_Traceguids, (unsigned int)v15);
LABEL_34:
  free(v3);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180013544  mov     [rsp-38h+arg_8], rbx
0x180013549  mov     [rsp-38h+arg_0], rcx
0x18001354e  push    rbp
0x18001354f  push    rsi
0x180013550  push    rdi
0x180013551  push    r12
0x180013553  push    r13
0x180013555  push    r14
0x180013557  push    r15
0x180013559  mov     rbp, rsp
0x18001355c  sub     rsp, 40h
0x180013560  mov     rax, rcx
0x180013563  xor     esi, esi
0x180013565  lea     rcx, [rbp+pszSrc]
0x180013569  or      r12, 0FFFFFFFFFFFFFFFFh
0x18001356d  mov     ebx, esi
0x18001356f  mov     r13, rdx
0x180013572  mov     [rbp+pszSrc], rbx
0x180013576  cmp     rax, rcx
0x180013579  jz      loc_180013607
0x18001357f  mov     rsi, [rax]
0x180013582  xor     ecx, ecx; Block
0x180013584  test    rsi, rsi
0x180013587  jz      loc_1800137EA
0x18001358d  mov     rax, r12
0x180013590  inc     rax
0x180013593  cmp     [rsi+rax*2], cx
0x180013597  jnz     short loc_180013590
0x180013599  lea     r15, [rax+1]
0x18001359d  lea     rcx, [r15+r15]; Size
0x1800135a1  call    cs:__imp_malloc
0x1800135a7  xor     r11d, r11d
0x1800135aa  mov     r14, rax
0x1800135ad  test    rax, rax
0x1800135b0  jz      loc_1800137F7
0x1800135b6  mov     rdx, r15; cchDest
0x1800135b9  call    StringValidateDestW
0x1800135be  mov     edi, eax
0x1800135c0  test    eax, eax
0x1800135c2  js      loc_1800137FE
0x1800135c8  mov     r9, rsi; pszSrc
0x1800135cb  mov     rcx, r14; pszDest
0x1800135ce  call    StringCopyWorkerW
0x1800135d3  mov     esi, eax
0x1800135d5  mov     edi, esi
0x1800135d7  test    esi, esi
0x1800135d9  js      loc_18001380D
0x1800135df  xor     ecx, ecx; Block
0x1800135e1  call    cs:__imp_free
0x1800135e7  mov     rbx, r14
0x1800135ea  mov     [rbp+pszSrc], rbx
0x1800135ee  test    esi, esi
0x1800135f0  jnz     loc_1800137AC
0x1800135f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800135fd  xor     esi, esi
0x1800135ff  test    edi, edi
0x180013601  js      loc_180013830
0x180013607  lea     rcx, [rbp+pszSrc]; struct CUString *
0x18001360b  call    ?HrEnsurePathBackslash@@YAJAEAVCUString@@@Z; HrEnsurePathBackslash(CUString &)
0x180013610  mov     edi, eax
0x180013612  test    eax, eax
0x180013614  js      loc_18001377C
0x18001361a  mov     rbx, [rbp+pszSrc]
0x18001361e  test    r13, r13
0x180013621  jz      loc_18001374C
0x180013627  test    rbx, rbx
0x18001362a  jz      loc_1800137A4
0x180013630  mov     rax, r12
0x180013633  inc     rax
0x180013636  cmp     [rbx+rax*2], si
0x18001363a  jnz     short loc_180013633
0x18001363c  inc     r12
0x18001363f  cmp     [r13+r12*2+0], si
0x180013645  jnz     short loc_18001363C
0x180013647  lea     r14, [rax+1]
0x18001364b  add     r14, r12
0x18001364e  lea     rcx, [r14+r14]; Size
0x180013652  call    cs:__imp_malloc
0x180013658  mov     r15, rax
0x18001365b  test    rax, rax
0x18001365e  jz      loc_180013818
0x180013664  mov     [rax], si
0x180013667  test    rbx, rbx
0x18001366a  jz      short loc_18001368F
0x18001366c  mov     rdx, r14; cchDest
0x18001366f  call    StringValidateDestW
0x180013674  mov     edi, eax
0x180013676  test    eax, eax
0x180013678  js      loc_180013822
0x18001367e  mov     r9, rbx; pszSrc
0x180013681  mov     rcx, r15; pszDest
0x180013684  call    StringCopyWorkerW
0x180013689  mov     edi, eax
0x18001368b  test    edi, edi
0x18001368d  js      short loc_1800136C6
0x18001368f  lea     r8, [rbp+pcchDestLength]; pcchDestLength
0x180013693  mov     [rbp+pcchDestLength], rsi
0x180013697  mov     rdx, r14; cchDest
0x18001369a  mov     rcx, r15; pszDest
0x18001369d  call    StringValidateDestAndLengthW
0x1800136a2  mov     esi, eax
0x1800136a4  test    eax, eax
0x1800136a6  js      short loc_1800136C0
0x1800136a8  mov     rax, [rbp+pcchDestLength]
0x1800136ac  mov     r9, r13; pszSrc
0x1800136af  sub     r14, rax
0x1800136b2  mov     rdx, r14; cchDest
0x1800136b5  lea     rcx, [r15+rax*2]; pszDest
0x1800136b9  call    StringCopyWorkerW
0x1800136be  mov     esi, eax
0x1800136c0  mov     edi, esi
0x1800136c2  test    esi, esi
0x1800136c4  jns     short loc_180013702
0x1800136c6  mov     rcx, r15; Block
0x1800136c9  call    cs:__imp_free
0x1800136cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800136d6  lea     rax, WPP_GLOBAL_Control
0x1800136dd  cmp     rcx, rax
0x1800136e0  jz      short loc_18001371D
0x1800136e2  test    byte ptr [rcx+1Ch], 1
0x1800136e6  jz      short loc_18001371D
0x1800136e8  mov     rcx, [rcx+10h]
0x1800136ec  lea     r8, WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids
0x1800136f3  mov     edx, 0Ch
0x1800136f8  mov     r9d, edi
0x1800136fb  call    WPP_SF_d
0x180013700  jmp     short loc_180013716
0x180013702  mov     rcx, rbx; Block
0x180013705  call    cs:__imp_free
0x18001370b  mov     rbx, r15
0x18001370e  mov     [rbp+pszSrc], rbx
0x180013712  test    esi, esi
0x180013714  jnz     short loc_1800136CF
0x180013716  mov     rcx, cs:WPP_GLOBAL_Control
0x18001371d  xor     esi, esi
0x18001371f  test    edi, edi
0x180013721  jns     short loc_18001374C
0x180013723  jnz     loc_180013830
0x180013729  mov     rcx, rbx; Block
0x18001372c  call    cs:__imp_free
0x180013732  mov     rbx, [rsp+40h+arg_8]
0x18001373a  mov     eax, edi
0x18001373c  add     rsp, 40h
0x180013740  pop     r15
0x180013742  pop     r14
0x180013744  pop     r13
0x180013746  pop     r12
0x180013748  pop     rdi
0x180013749  pop     rsi
0x18001374a  pop     rbp
0x18001374b  retn
0x18001374c  xor     edx, edx; lpSecurityAttributes
0x18001374e  mov     rcx, rbx; lpPathName
0x180013751  call    cs:__imp_CreateDirectoryW
0x180013757  test    eax, eax
0x180013759  jnz     short loc_18001376D
0x18001375b  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180013760  mov     edi, eax
0x180013762  cmp     eax, 800700B7h
0x180013767  jz      short loc_18001376D
0x180013769  test    eax, eax
0x18001376b  js      short loc_180013780
0x18001376d  lea     rcx, [rbp+pszSrc]; struct CUString *
0x180013771  call    ?HrEnsurePathBackslash@@YAJAEAVCUString@@@Z; HrEnsurePathBackslash(CUString &)
0x180013776  mov     edi, eax
0x180013778  test    eax, eax
0x18001377a  jns     short loc_18001378B
0x18001377c  mov     rbx, [rbp+pszSrc]
0x180013780  mov     rcx, cs:WPP_GLOBAL_Control
0x180013787  test    edi, edi
0x180013789  jmp     short loc_180013723
0x18001378b  mov     rbx, [rbp+arg_0]
0x18001378f  mov     rcx, [rbx]; Block
0x180013792  call    cs:__imp_free
0x180013798  mov     rax, [rbp+pszSrc]
0x18001379c  mov     [rbx], rax
0x18001379f  mov     rbx, rsi
0x1800137a2  jmp     short loc_180013780
0x1800137a4  mov     rax, rsi
0x1800137a7  jmp     loc_18001363C
0x1800137ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800137b3  lea     rax, WPP_GLOBAL_Control
0x1800137ba  cmp     rcx, rax
0x1800137bd  jz      loc_1800135FD
0x1800137c3  test    byte ptr [rcx+1Ch], 1
0x1800137c7  jz      loc_1800135FD
0x1800137cd  mov     rcx, [rcx+10h]
0x1800137d1  lea     r8, WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids
0x1800137d8  mov     edx, 0Ah
0x1800137dd  mov     r9d, edi
0x1800137e0  call    WPP_SF_d
0x1800137e5  jmp     loc_1800135F6
0x1800137ea  call    cs:__imp_free
0x1800137f0  xor     esi, esi
0x1800137f2  jmp     loc_180013607
0x1800137f7  mov     edi, 8007000Eh
0x1800137fc  jmp     short loc_1800137AC
0x1800137fe  mov     esi, eax
0x180013800  test    r15, r15
0x180013803  jz      loc_1800135D5
0x180013809  mov     [r14], r11w
0x18001380d  mov     rcx, r14; Block
0x180013810  call    cs:__imp_free
0x180013816  jmp     short loc_1800137AC
0x180013818  mov     edi, 8007000Eh
0x18001381d  jmp     loc_1800136CF
0x180013822  test    r14, r14
0x180013825  jnz     loc_1800136C6
0x18001382b  jmp     loc_18001368B
0x180013830  lea     rax, WPP_GLOBAL_Control
0x180013837  cmp     rcx, rax
0x18001383a  jz      loc_180013729
0x180013840  test    byte ptr [rcx+1Ch], 1
0x180013844  jz      loc_180013729
0x18001384a  mov     rcx, [rcx+10h]
0x18001384e  lea     r8, WPP_cd0457ca62d634003859bdcf9006b616_Traceguids
0x180013855  mov     edx, 16h
0x18001385a  mov     r9d, edi
0x18001385d  call    WPP_SF_d
0x180013862  jmp     loc_180013729
```
