# HrAddDirectoryToPath(CUString &,ushort const *)

- ea: `0x1800075ac`
- end: `0x18000790c`
- name: `?HrAddDirectoryToPath@@YAJAEAVCUString@@PEBG@Z`
- size: `864`
- prototype: `__int64 __fastcall(void **, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x1800106a8`
- `0x180013818`
- `0x180015794`

## callees

- `0x1800074dc`
- `0x1800075ac`
- `0x180007c0c`
- `0x18003a798`
- `0x18003b1cc`
- `0x180045b90`
- `0x180045be8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000764f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007743`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007785`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800077b2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007825`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007883`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800078af`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000764f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007743`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007785`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800077b2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007825`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007883`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800078af`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180007609`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800076c6`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180007609`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800076c6`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800077de`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800077de`

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
0x1800075ac  mov     [rsp-38h+arg_8], rbx
0x1800075b1  mov     [rsp-38h+arg_0], rcx
0x1800075b6  push    rbp
0x1800075b7  push    rsi
0x1800075b8  push    rdi
0x1800075b9  push    r12
0x1800075bb  push    r13
0x1800075bd  push    r14
0x1800075bf  push    r15
0x1800075c1  mov     rbp, rsp
0x1800075c4  sub     rsp, 40h
0x1800075c8  mov     rax, rcx
0x1800075cb  xor     esi, esi
0x1800075cd  lea     rcx, [rbp+pszSrc]
0x1800075d1  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800075d5  mov     ebx, esi
0x1800075d7  mov     r13, rdx
0x1800075da  mov     [rbp+pszSrc], rbx
0x1800075de  cmp     rax, rcx
0x1800075e1  jz      loc_18000767B
0x1800075e7  mov     rsi, [rax]
0x1800075ea  xor     ecx, ecx; Block
0x1800075ec  test    rsi, rsi
0x1800075ef  jz      loc_180007883
0x1800075f5  mov     rax, r12
0x1800075f8  inc     rax
0x1800075fb  cmp     [rsi+rax*2], cx
0x1800075ff  jnz     short loc_1800075F8
0x180007601  lea     r15, [rax+1]
0x180007605  lea     rcx, [r15+r15]; Size
0x180007609  call    cs:__imp_malloc
0x180007610  nop     dword ptr [rax+rax+00h]
0x180007615  xor     r11d, r11d
0x180007618  mov     r14, rax
0x18000761b  test    rax, rax
0x18000761e  jz      loc_180007896
0x180007624  mov     rdx, r15; cchDest
0x180007627  call    StringValidateDestW
0x18000762c  mov     edi, eax
0x18000762e  test    eax, eax
0x180007630  js      loc_18000789D
0x180007636  mov     r9, rsi; pszSrc
0x180007639  mov     rcx, r14; pszDest
0x18000763c  call    StringCopyWorkerW
0x180007641  mov     esi, eax
0x180007643  mov     edi, esi
0x180007645  test    esi, esi
0x180007647  js      loc_1800078AC
0x18000764d  xor     ecx, ecx; Block
0x18000764f  call    cs:__imp_free
0x180007656  nop     dword ptr [rax+rax+00h]
0x18000765b  mov     rbx, r14
0x18000765e  mov     [rbp+pszSrc], rbx
0x180007662  test    esi, esi
0x180007664  jnz     loc_180007845
0x18000766a  mov     rcx, cs:WPP_GLOBAL_Control
0x180007671  xor     esi, esi
0x180007673  test    edi, edi
0x180007675  js      loc_1800078D5
0x18000767b  lea     rcx, [rbp+pszSrc]; struct CUString *
0x18000767f  call    ?HrEnsurePathBackslash@@YAJAEAVCUString@@@Z; HrEnsurePathBackslash(CUString &)
0x180007684  mov     edi, eax
0x180007686  test    eax, eax
0x180007688  js      loc_18000780F
0x18000768e  mov     rbx, [rbp+pszSrc]
0x180007692  test    r13, r13
0x180007695  jz      loc_1800077D9
0x18000769b  test    rbx, rbx
0x18000769e  jz      loc_18000783D
0x1800076a4  mov     rax, r12
0x1800076a7  inc     rax
0x1800076aa  cmp     [rbx+rax*2], si
0x1800076ae  jnz     short loc_1800076A7
0x1800076b0  inc     r12
0x1800076b3  cmp     [r13+r12*2+0], si
0x1800076b9  jnz     short loc_1800076B0
0x1800076bb  lea     r14, [rax+1]
0x1800076bf  add     r14, r12
0x1800076c2  lea     rcx, [r14+r14]; Size
0x1800076c6  call    cs:__imp_malloc
0x1800076cd  nop     dword ptr [rax+rax+00h]
0x1800076d2  mov     r15, rax
0x1800076d5  test    rax, rax
0x1800076d8  jz      loc_1800078BD
0x1800076de  mov     [rax], si
0x1800076e1  test    rbx, rbx
0x1800076e4  jz      short loc_180007709
0x1800076e6  mov     rdx, r14; cchDest
0x1800076e9  call    StringValidateDestW
0x1800076ee  mov     edi, eax
0x1800076f0  test    eax, eax
0x1800076f2  js      loc_1800078C7
0x1800076f8  mov     r9, rbx; pszSrc
0x1800076fb  mov     rcx, r15; pszDest
0x1800076fe  call    StringCopyWorkerW
0x180007703  mov     edi, eax
0x180007705  test    edi, edi
0x180007707  js      short loc_180007740
0x180007709  lea     r8, [rbp+pcchDestLength]; pcchDestLength
0x18000770d  mov     [rbp+pcchDestLength], rsi
0x180007711  mov     rdx, r14; cchDest
0x180007714  mov     rcx, r15; pszDest
0x180007717  call    StringValidateDestAndLengthW
0x18000771c  mov     esi, eax
0x18000771e  test    eax, eax
0x180007720  js      short loc_18000773A
0x180007722  mov     rax, [rbp+pcchDestLength]
0x180007726  mov     r9, r13; pszSrc
0x180007729  sub     r14, rax
0x18000772c  mov     rdx, r14; cchDest
0x18000772f  lea     rcx, [r15+rax*2]; pszDest
0x180007733  call    StringCopyWorkerW
0x180007738  mov     esi, eax
0x18000773a  mov     edi, esi
0x18000773c  test    esi, esi
0x18000773e  jns     short loc_180007782
0x180007740  mov     rcx, r15; Block
0x180007743  call    cs:__imp_free
0x18000774a  nop     dword ptr [rax+rax+00h]
0x18000774f  mov     rcx, cs:WPP_GLOBAL_Control
0x180007756  lea     rax, WPP_GLOBAL_Control
0x18000775d  cmp     rcx, rax
0x180007760  jz      short loc_1800077A3
0x180007762  test    byte ptr [rcx+1Ch], 1
0x180007766  jz      short loc_1800077A3
0x180007768  mov     rcx, [rcx+10h]
0x18000776c  lea     r8, WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids
0x180007773  mov     edx, 0Ch
0x180007778  mov     r9d, edi
0x18000777b  call    WPP_SF_d
0x180007780  jmp     short loc_18000779C
0x180007782  mov     rcx, rbx; Block
0x180007785  call    cs:__imp_free
0x18000778c  nop     dword ptr [rax+rax+00h]
0x180007791  mov     rbx, r15
0x180007794  mov     [rbp+pszSrc], rbx
0x180007798  test    esi, esi
0x18000779a  jnz     short loc_18000774F
0x18000779c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800077a3  xor     esi, esi
0x1800077a5  test    edi, edi
0x1800077a7  jns     short loc_1800077D9
0x1800077a9  jnz     loc_1800078D5
0x1800077af  mov     rcx, rbx; Block
0x1800077b2  call    cs:__imp_free
0x1800077b9  nop     dword ptr [rax+rax+00h]
0x1800077be  mov     rbx, [rsp+40h+arg_8]
0x1800077c6  mov     eax, edi
0x1800077c8  add     rsp, 40h
0x1800077cc  pop     r15
0x1800077ce  pop     r14
0x1800077d0  pop     r13
0x1800077d2  pop     r12
0x1800077d4  pop     rdi
0x1800077d5  pop     rsi
0x1800077d6  pop     rbp
0x1800077d7  retn
0x1800077d9  xor     edx, edx; lpSecurityAttributes
0x1800077db  mov     rcx, rbx; lpPathName
0x1800077de  call    cs:__imp_CreateDirectoryW
0x1800077e5  nop     dword ptr [rax+rax+00h]
0x1800077ea  test    eax, eax
0x1800077ec  jnz     short loc_180007800
0x1800077ee  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x1800077f3  mov     edi, eax
0x1800077f5  cmp     eax, 800700B7h
0x1800077fa  jz      short loc_180007800
0x1800077fc  test    eax, eax
0x1800077fe  js      short loc_180007813
0x180007800  lea     rcx, [rbp+pszSrc]; struct CUString *
0x180007804  call    ?HrEnsurePathBackslash@@YAJAEAVCUString@@@Z; HrEnsurePathBackslash(CUString &)
0x180007809  mov     edi, eax
0x18000780b  test    eax, eax
0x18000780d  jns     short loc_18000781E
0x18000780f  mov     rbx, [rbp+pszSrc]
0x180007813  mov     rcx, cs:WPP_GLOBAL_Control
0x18000781a  test    edi, edi
0x18000781c  jmp     short loc_1800077A9
0x18000781e  mov     rbx, [rbp+arg_0]
0x180007822  mov     rcx, [rbx]; Block
0x180007825  call    cs:__imp_free
0x18000782c  nop     dword ptr [rax+rax+00h]
0x180007831  mov     rax, [rbp+pszSrc]
0x180007835  mov     [rbx], rax
0x180007838  mov     rbx, rsi
0x18000783b  jmp     short loc_180007813
0x18000783d  mov     rax, rsi
0x180007840  jmp     loc_1800076B0
0x180007845  mov     rcx, cs:WPP_GLOBAL_Control
0x18000784c  lea     rax, WPP_GLOBAL_Control
0x180007853  cmp     rcx, rax
0x180007856  jz      loc_180007671
0x18000785c  test    byte ptr [rcx+1Ch], 1
0x180007860  jz      loc_180007671
0x180007866  mov     rcx, [rcx+10h]
0x18000786a  lea     r8, WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids
0x180007871  mov     edx, 0Ah
0x180007876  mov     r9d, edi
0x180007879  call    WPP_SF_d
0x18000787e  jmp     loc_18000766A
0x180007883  call    cs:__imp_free
0x18000788a  nop     dword ptr [rax+rax+00h]
0x18000788f  xor     esi, esi
0x180007891  jmp     loc_18000767B
0x180007896  mov     edi, 8007000Eh
0x18000789b  jmp     short loc_180007845
0x18000789d  mov     esi, eax
0x18000789f  test    r15, r15
0x1800078a2  jz      loc_180007643
0x1800078a8  mov     [r14], r11w
0x1800078ac  mov     rcx, r14; Block
0x1800078af  call    cs:__imp_free
0x1800078b6  nop     dword ptr [rax+rax+00h]
0x1800078bb  jmp     short loc_180007845
0x1800078bd  mov     edi, 8007000Eh
0x1800078c2  jmp     loc_18000774F
0x1800078c7  test    r14, r14
0x1800078ca  jnz     loc_180007740
0x1800078d0  jmp     loc_180007705
0x1800078d5  lea     rax, WPP_GLOBAL_Control
0x1800078dc  cmp     rcx, rax
0x1800078df  jz      loc_1800077AF
0x1800078e5  test    byte ptr [rcx+1Ch], 1
0x1800078e9  jz      loc_1800077AF
0x1800078ef  mov     rcx, [rcx+10h]
0x1800078f3  lea     r8, WPP_cd0457ca62d634003859bdcf9006b616_Traceguids
0x1800078fa  mov     edx, 16h
0x1800078ff  mov     r9d, edi
0x180007902  call    WPP_SF_d
0x180007907  jmp     loc_1800077AF
```
