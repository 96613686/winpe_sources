# SdpLocalizeDisplayInformation(Settings *,_SDIAG_DISPINFO *,int)

- ea: `0x18000615c`
- end: `0x18000661a`
- name: `?SdpLocalizeDisplayInformation@@YAJPEAVSettings@@PEAU_SDIAG_DISPINFO@@H@Z`
- size: `1214`
- prototype: `__int64 __fastcall(struct Settings *, const unsigned __int16 **, int)`
- caller_count: `5`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x180016630`
- `0x18001a530`
- `0x18001c6e8`
- `0x1800208f4`
- `0x180022ce0`

## callees

- `0x1800012a4`
- `0x1800020f8`
- `0x180005ffc`
- `0x18000615c`
- `0x180006620`
- `0x18001e808`
- `0x180026fa0`
- `0x18002758c`
- `0x180027aa0`
- `0x180027b7c`

## import_xrefs

- `msvcrt!wcschr` at `0x1800062ff`
- `msvcrt!wcschr` at `0x1800064b5`
- `msvcrt!wcschr` at `0x1800062ff`
- `msvcrt!wcschr` at `0x1800064b5`
- `msvcrt!_wcsicmp` at `0x180006372`
- `msvcrt!_wcsicmp` at `0x180006396`
- `msvcrt!_wcsicmp` at `0x180006372`
- `msvcrt!_wcsicmp` at `0x180006396`
- `KERNEL32!GetLastError` at `0x1800062c6`
- `KERNEL32!GetLastError` at `0x18000647c`
- `KERNEL32!GetLastError` at `0x1800062c6`
- `KERNEL32!GetLastError` at `0x18000647c`
- `OLEAUT32!__imp_SysAllocString` at `0x180006556`
- `OLEAUT32!__imp_SysAllocString` at `0x18000658b`
- `OLEAUT32!__imp_SysAllocString` at `0x180006556`
- `OLEAUT32!__imp_SysAllocString` at `0x18000658b`
- `OLEAUT32!__imp_SysFreeString` at `0x180006545`
- `OLEAUT32!__imp_SysFreeString` at `0x18000657a`
- `OLEAUT32!__imp_SysFreeString` at `0x180006545`
- `OLEAUT32!__imp_SysFreeString` at `0x18000657a`

## pseudocode

```c
__int64 __fastcall SdpLocalizeDisplayInformation(struct Settings *a1, const unsigned __int16 **a2, int a3)
{
  unsigned __int16 *v3; // r14
  unsigned int v6; // r8d
  signed int v7; // ebx
  int PackagePath; // eax
  unsigned __int16 *v9; // r15
  int v10; // eax
  void *v11; // rsi
  int IsSubDirectory; // eax
  unsigned int v13; // r8d
  int v14; // r9d
  signed int LastError; // eax
  wchar_t *v16; // rbx
  int v17; // eax
  int v18; // r9d
  unsigned int v19; // r8d
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  signed int v24; // eax
  wchar_t *v25; // rbx
  int v26; // eax
  int v27; // eax
  int v28; // eax
  BSTR v29; // rax
  OLECHAR *v30; // rcx
  BSTR v31; // rax
  unsigned __int16 *v33; // [rsp+20h] [rbp-30h] BYREF
  void *Block; // [rsp+28h] [rbp-28h] BYREF
  wchar_t *Str; // [rsp+30h] [rbp-20h] BYREF
  OLECHAR *psz; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int16 *v37; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int16 *v38; // [rsp+48h] [rbp-8h] BYREF
  int v39; // [rsp+80h] [rbp+30h] BYREF
  unsigned int v40; // [rsp+98h] [rbp+48h] BYREF

  v3 = 0;
  psz = 0;
  v37 = 0;
  Block = 0;
  v38 = 0;
  v33 = 0;
  Str = 0;
  v40 = 0;
  v39 = 0;
  if ( !a1 )
  {
    v6 = 61;
LABEL_3:
    v7 = -2147024809;
    SdpDebugTrace(1u, L"SdpLocalizeDisplayInformation", v6, -2147024809);
    return (unsigned int)v7;
  }
  if ( !a2 )
  {
    v6 = 62;
    goto LABEL_3;
  }
  v7 = 0;
  if ( (*((_BYTE *)a1 + 56) & 4) == 0 )
    return (unsigned int)v7;
  PackagePath = Settings::get_PackagePath(a1, &v38);
  v9 = v38;
  v7 = PackagePath;
  if ( PackagePath >= 0 )
  {
    v10 = SdpStrCpy((unsigned __int16 **)&Block, *a2);
    v7 = v10;
    if ( v10 < 0 )
    {
      SdpDebugTrace(1u, L"SdpLocalizeDisplayInformation", 0x53u, v10);
      v11 = Block;
      goto LABEL_79;
    }
    v11 = Block;
    IsSubDirectory = SdpParseResourceDescriptor((unsigned __int16 *)Block, &Str, &v40);
    v7 = IsSubDirectory;
    if ( IsSubDirectory < 0 )
    {
      v13 = 86;
LABEL_13:
      v14 = IsSubDirectory;
LABEL_14:
      SdpDebugTrace(1u, L"SdpLocalizeDisplayInformation", v13, v14);
LABEL_79:
      if ( v11 )
        operator delete(v11);
      goto LABEL_81;
    }
    if ( a3 )
    {
      IsSubDirectory = SdpBuildPath(v9, Str, &v33);
      v7 = IsSubDirectory;
      if ( IsSubDirectory < 0 )
      {
        v13 = 90;
        goto LABEL_13;
      }
      IsSubDirectory = SdpIsSubDirectory(v9, v33, &v39);
      v7 = IsSubDirectory;
      if ( IsSubDirectory < 0 )
      {
        v13 = 97;
        goto LABEL_13;
      }
      if ( !v39 )
      {
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        v13 = 98;
        if ( v7 >= 0 )
          v7 = -2147467259;
        v14 = v7;
        goto LABEL_14;
      }
    }
    else
    {
      v16 = Str;
      if ( wcschr(Str, 0x5Cu) )
      {
        IsSubDirectory = SdpStrExpand(&v33, v16);
        v7 = IsSubDirectory;
        if ( IsSubDirectory < 0 )
        {
          v13 = 106;
          goto LABEL_13;
        }
      }
      else
      {
        IsSubDirectory = SdpBuildPath(v9, v16, &v33);
        v7 = IsSubDirectory;
        if ( IsSubDirectory < 0 )
        {
          v13 = 110;
          goto LABEL_13;
        }
      }
    }
    v17 = SdpLoadString(v33, v40, &psz);
    v7 = v17;
    if ( v17 < 0 )
    {
      v18 = v17;
      v19 = 115;
LABEL_74:
      SdpDebugTrace(1u, L"SdpLocalizeDisplayInformation", v19, v18);
      goto LABEL_75;
    }
    if ( !_wcsicmp(*a2, &word_18002DFCC) )
    {
      v18 = -2147024809;
      v19 = 123;
LABEL_73:
      v7 = v18;
      goto LABEL_74;
    }
    if ( _wcsicmp(a2[1], &word_18002DFCC) )
    {
      if ( v11 )
      {
        operator delete(v11);
        Block = 0;
      }
      if ( v33 )
      {
        operator delete(v33);
        v33 = 0;
      }
      v20 = SdpStrCpy((unsigned __int16 **)&Block, a2[1]);
      v7 = v20;
      if ( v20 < 0 )
      {
        SdpDebugTrace(1u, L"SdpLocalizeDisplayInformation", 0x87u, v20);
        v11 = Block;
LABEL_75:
        if ( psz )
          operator delete(psz);
        if ( v3 )
          operator delete(v3);
        goto LABEL_79;
      }
      v11 = Block;
      v21 = SdpParseResourceDescriptor((unsigned __int16 *)Block, &Str, &v40);
      v7 = v21;
      if ( v21 < 0 )
      {
        v18 = v21;
        v19 = 138;
        goto LABEL_74;
      }
      if ( a3 )
      {
        v22 = SdpBuildPath(v9, Str, &v33);
        v7 = v22;
        if ( v22 < 0 )
        {
          v18 = v22;
          v19 = 142;
          goto LABEL_74;
        }
        v23 = SdpIsSubDirectory(v9, v33, &v39);
        v7 = v23;
        if ( v23 < 0 )
        {
          v18 = v23;
          v19 = 149;
          goto LABEL_74;
        }
        if ( !v39 )
        {
          v24 = GetLastError();
          v7 = v24;
          if ( v24 > 0 )
            v7 = (unsigned __int16)v24 | 0x80070000;
          v19 = 150;
          if ( v7 >= 0 )
            v7 = -2147467259;
          v18 = v7;
          goto LABEL_74;
        }
      }
      else
      {
        v25 = Str;
        if ( wcschr(Str, 0x5Cu) )
        {
          v26 = SdpStrExpand(&v33, v25);
          v7 = v26;
          if ( v26 < 0 )
          {
            v18 = v26;
            v19 = 158;
            goto LABEL_74;
          }
        }
        else
        {
          v27 = SdpBuildPath(v9, v25, &v33);
          v7 = v27;
          if ( v27 < 0 )
          {
            v18 = v27;
            v19 = 162;
            goto LABEL_74;
          }
        }
      }
      v28 = SdpLoadString(v33, v40, &v37);
      v7 = v28;
      if ( v28 < 0 )
      {
        SdpDebugTrace(1u, L"SdpLocalizeDisplayInformation", 0xA7u, v28);
        v3 = v37;
        goto LABEL_75;
      }
      v3 = v37;
    }
    if ( *a2 )
    {
      SysFreeString((BSTR)*a2);
      *a2 = 0;
    }
    v29 = SysAllocString(psz);
    *a2 = v29;
    if ( v29 )
    {
      if ( !v3 )
        goto LABEL_75;
      v30 = (OLECHAR *)a2[1];
      if ( v30 )
      {
        SysFreeString(v30);
        a2[1] = 0;
      }
      v31 = SysAllocString(v3);
      a2[1] = v31;
      if ( v31 )
        goto LABEL_75;
      v19 = 181;
    }
    else
    {
      v19 = 176;
    }
    v18 = -2147024882;
    goto LABEL_73;
  }
  SdpDebugTrace(1u, L"SdpLocalizeDisplayInformation", 0x4Cu, PackagePath);
LABEL_81:
  if ( v9 )
    operator delete(v9);
  if ( v33 )
    operator delete(v33);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000615c  mov     [rsp-28h+arg_8], rbx
0x180006161  mov     [rsp-28h+arg_10], rsi
0x180006166  push    rbp
0x180006167  push    rdi
0x180006168  push    r12
0x18000616a  push    r14
0x18000616c  push    r15
0x18000616e  mov     rbp, rsp
0x180006171  sub     rsp, 50h
0x180006175  xor     r14d, r14d
0x180006178  mov     [rbp+psz], 0
0x180006180  mov     [rbp+var_10], r14
0x180006184  mov     r12d, r8d
0x180006187  mov     [rbp+Block], r14
0x18000618b  mov     rdi, rdx
0x18000618e  mov     [rbp+var_8], r14
0x180006192  mov     [rbp+var_30], r14
0x180006196  mov     [rbp+Str], r14
0x18000619a  mov     [rbp+arg_18], r14d
0x18000619e  mov     [rbp+arg_0], r14d
0x1800061a2  test    rcx, rcx
0x1800061a5  jnz     short loc_1800061CA
0x1800061a7  lea     r8d, [r14+3Dh]; int
0x1800061ab  mov     r9d, 80070057h; int
0x1800061b1  lea     rdx, aSdplocalizedis; "SdpLocalizeDisplayInformation"
0x1800061b8  mov     ecx, 1; Level
0x1800061bd  mov     ebx, r9d
0x1800061c0  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800061c5  jmp     loc_1800065FF
0x1800061ca  test    rdi, rdi
0x1800061cd  jnz     short loc_1800061D5
0x1800061cf  lea     r8d, [rdi+3Eh]
0x1800061d3  jmp     short loc_1800061AB
0x1800061d5  xor     ebx, ebx
0x1800061d7  test    byte ptr [rcx+38h], 4
0x1800061db  jz      loc_1800065FF
0x1800061e1  lea     rdx, [rbp+var_8]; unsigned __int16 **
0x1800061e5  call    ?get_PackagePath@Settings@@QEAAJPEAPEAG@Z; Settings::get_PackagePath(ushort * *)
0x1800061ea  mov     r15, [rbp+var_8]
0x1800061ee  mov     ebx, eax
0x1800061f0  test    eax, eax
0x1800061f2  jns     short loc_180006212
0x1800061f4  mov     r8d, 4Ch ; 'L'; int
0x1800061fa  lea     rdx, aSdplocalizedis; "SdpLocalizeDisplayInformation"
0x180006201  mov     r9d, eax; int
0x180006204  lea     ecx, [r8-4Bh]; Level
0x180006208  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000620d  jmp     loc_1800065E4
0x180006212  mov     rdx, [rdi]; unsigned __int16 *
0x180006215  lea     rcx, [rbp+Block]; unsigned __int16 **
0x180006219  call    ?SdpStrCpy@@YAJPEAPEAGPEBG@Z; SdpStrCpy(ushort * *,ushort const *)
0x18000621e  mov     ebx, eax
0x180006220  test    eax, eax
0x180006222  jns     short loc_180006246
0x180006224  mov     r8d, 53h ; 'S'; int
0x18000622a  lea     rdx, aSdplocalizedis; "SdpLocalizeDisplayInformation"
0x180006231  mov     r9d, eax; int
0x180006234  lea     ecx, [r8-52h]; Level
0x180006238  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000623d  mov     rsi, [rbp+Block]
0x180006241  jmp     loc_1800065D7
0x180006246  mov     rsi, [rbp+Block]
0x18000624a  lea     r8, [rbp+arg_18]; unsigned int *
0x18000624e  mov     rcx, rsi; unsigned __int16 *
0x180006251  lea     rdx, [rbp+Str]; unsigned __int16 **
0x180006255  call    ?SdpParseResourceDescriptor@@YAJPEAGPEAPEAGPEAK@Z; SdpParseResourceDescriptor(ushort *,ushort * *,ulong *)
0x18000625a  mov     ebx, eax
0x18000625c  test    eax, eax
0x18000625e  jns     short loc_18000627F
0x180006260  mov     r8d, 56h ; 'V'; int
0x180006266  mov     r9d, eax; int
0x180006269  lea     rdx, aSdplocalizedis; "SdpLocalizeDisplayInformation"
0x180006270  mov     ecx, 1; Level
0x180006275  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000627a  jmp     loc_1800065D7
0x18000627f  test    r12d, r12d
0x180006282  jz      short loc_1800062F3
0x180006284  mov     rdx, [rbp+Str]; unsigned __int16 *
0x180006288  lea     r8, [rbp+var_30]; unsigned __int16 **
0x18000628c  mov     rcx, r15; unsigned __int16 *
0x18000628f  call    ?SdpBuildPath@@YAJPEBG0PEAPEAG@Z; SdpBuildPath(ushort const *,ushort const *,ushort * *)
0x180006294  mov     ebx, eax
0x180006296  test    eax, eax
0x180006298  jns     short loc_1800062A2
0x18000629a  mov     r8d, 5Ah ; 'Z'
0x1800062a0  jmp     short loc_180006266
0x1800062a2  mov     rdx, [rbp+var_30]; unsigned __int16 *
0x1800062a6  lea     r8, [rbp+arg_0]; int *
0x1800062aa  mov     rcx, r15; unsigned __int16 *
0x1800062ad  call    ?SdpIsSubDirectory@@YAJPEBG0PEAH@Z; SdpIsSubDirectory(ushort const *,ushort const *,int *)
0x1800062b2  mov     ebx, eax
0x1800062b4  test    eax, eax
0x1800062b6  jns     short loc_1800062C0
0x1800062b8  mov     r8d, 61h ; 'a'
0x1800062be  jmp     short loc_180006266
0x1800062c0  cmp     [rbp+arg_0], r14d
0x1800062c4  jnz     short loc_180006344
0x1800062c6  call    cs:__imp_GetLastError
0x1800062cc  mov     ebx, eax
0x1800062ce  test    eax, eax
0x1800062d0  jle     short loc_1800062DB
0x1800062d2  movzx   ebx, ax
0x1800062d5  or      ebx, 80070000h
0x1800062db  test    ebx, ebx
0x1800062dd  mov     eax, 80004005h
0x1800062e2  mov     r8d, 62h ; 'b'
0x1800062e8  cmovns  ebx, eax
0x1800062eb  mov     r9d, ebx
0x1800062ee  jmp     loc_180006269
0x1800062f3  mov     rbx, [rbp+Str]
0x1800062f7  mov     edx, 5Ch ; '\'; Ch
0x1800062fc  mov     rcx, rbx; Str
0x1800062ff  call    cs:__imp_wcschr
0x180006305  mov     rdx, rbx; unsigned __int16 *
0x180006308  test    rax, rax
0x18000630b  jz      short loc_180006327
0x18000630d  lea     rcx, [rbp+var_30]; unsigned __int16 **
0x180006311  call    ?SdpStrExpand@@YAJPEAPEAGPEBG@Z; SdpStrExpand(ushort * *,ushort const *)
0x180006316  mov     ebx, eax
0x180006318  test    eax, eax
0x18000631a  jns     short loc_180006344
0x18000631c  mov     r8d, 6Ah ; 'j'
0x180006322  jmp     loc_180006266
0x180006327  lea     r8, [rbp+var_30]; unsigned __int16 **
0x18000632b  mov     rcx, r15; unsigned __int16 *
0x18000632e  call    ?SdpBuildPath@@YAJPEBG0PEAPEAG@Z; SdpBuildPath(ushort const *,ushort const *,ushort * *)
0x180006333  mov     ebx, eax
0x180006335  test    eax, eax
0x180006337  jns     short loc_180006344
0x180006339  mov     r8d, 6Eh ; 'n'
0x18000633f  jmp     loc_180006266
0x180006344  mov     edx, [rbp+arg_18]; unsigned int
0x180006347  lea     r8, [rbp+psz]; unsigned __int16 **
0x18000634b  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x18000634f  call    ?SdpLoadString@@YAJPEBGKPEAPEAG@Z; SdpLoadString(ushort const *,ulong,ushort * *)
0x180006354  mov     ebx, eax
0x180006356  test    eax, eax
0x180006358  jns     short loc_180006368
0x18000635a  mov     r9d, eax
0x18000635d  mov     r8d, 73h ; 's'
0x180006363  jmp     loc_1800065A9
0x180006368  mov     rcx, [rdi]; String1
0x18000636b  lea     rdx, word_18002DFCC; String2
0x180006372  call    cs:__imp__wcsicmp
0x180006378  test    eax, eax
0x18000637a  jnz     short loc_18000638B
0x18000637c  mov     r9d, 80070057h
0x180006382  lea     r8d, [rax+7Bh]
0x180006386  jmp     loc_1800065A6
0x18000638b  mov     rcx, [rdi+8]; String1
0x18000638f  lea     rdx, word_18002DFCC; String2
0x180006396  call    cs:__imp__wcsicmp
0x18000639c  test    eax, eax
0x18000639e  jz      loc_18000653D
0x1800063a4  test    rsi, rsi
0x1800063a7  jz      short loc_1800063B5
0x1800063a9  mov     rcx, rsi; Block
0x1800063ac  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800063b1  mov     [rbp+Block], r14
0x1800063b5  mov     rcx, [rbp+var_30]; Block
0x1800063b9  test    rcx, rcx
0x1800063bc  jz      short loc_1800063C7
0x1800063be  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800063c3  mov     [rbp+var_30], r14
0x1800063c7  mov     rdx, [rdi+8]; unsigned __int16 *
0x1800063cb  lea     rcx, [rbp+Block]; unsigned __int16 **
0x1800063cf  call    ?SdpStrCpy@@YAJPEAPEAGPEBG@Z; SdpStrCpy(ushort * *,ushort const *)
0x1800063d4  mov     ebx, eax
0x1800063d6  test    eax, eax
0x1800063d8  jns     short loc_1800063FD
0x1800063da  mov     r9d, eax; int
0x1800063dd  lea     rdx, aSdplocalizedis; "SdpLocalizeDisplayInformation"
0x1800063e4  mov     r8d, 87h; int
0x1800063ea  mov     ecx, 1; Level
0x1800063ef  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800063f4  mov     rsi, [rbp+Block]
0x1800063f8  jmp     loc_1800065BA
0x1800063fd  mov     rsi, [rbp+Block]
0x180006401  lea     r8, [rbp+arg_18]; unsigned int *
0x180006405  mov     rcx, rsi; unsigned __int16 *
0x180006408  lea     rdx, [rbp+Str]; unsigned __int16 **
0x18000640c  call    ?SdpParseResourceDescriptor@@YAJPEAGPEAPEAGPEAK@Z; SdpParseResourceDescriptor(ushort *,ushort * *,ulong *)
0x180006411  mov     ebx, eax
0x180006413  test    eax, eax
0x180006415  jns     short loc_180006425
0x180006417  mov     r9d, eax
0x18000641a  mov     r8d, 8Ah
0x180006420  jmp     loc_1800065A9
0x180006425  test    r12d, r12d
0x180006428  jz      short loc_1800064A9
0x18000642a  mov     rdx, [rbp+Str]; unsigned __int16 *
0x18000642e  lea     r8, [rbp+var_30]; unsigned __int16 **
0x180006432  mov     rcx, r15; unsigned __int16 *
0x180006435  call    ?SdpBuildPath@@YAJPEBG0PEAPEAG@Z; SdpBuildPath(ushort const *,ushort const *,ushort * *)
0x18000643a  mov     ebx, eax
0x18000643c  test    eax, eax
0x18000643e  jns     short loc_18000644E
0x180006440  mov     r9d, eax
0x180006443  mov     r8d, 8Eh
0x180006449  jmp     loc_1800065A9
0x18000644e  mov     rdx, [rbp+var_30]; unsigned __int16 *
0x180006452  lea     r8, [rbp+arg_0]; int *
0x180006456  mov     rcx, r15; unsigned __int16 *
0x180006459  call    ?SdpIsSubDirectory@@YAJPEBG0PEAH@Z; SdpIsSubDirectory(ushort const *,ushort const *,int *)
0x18000645e  mov     ebx, eax
0x180006460  test    eax, eax
0x180006462  jns     short loc_180006472
0x180006464  mov     r9d, eax
0x180006467  mov     r8d, 95h
0x18000646d  jmp     loc_1800065A9
0x180006472  cmp     [rbp+arg_0], r14d
0x180006476  jnz     loc_180006500
0x18000647c  call    cs:__imp_GetLastError
0x180006482  mov     ebx, eax
0x180006484  test    eax, eax
0x180006486  jle     short loc_180006491
0x180006488  movzx   ebx, ax
0x18000648b  or      ebx, 80070000h
0x180006491  test    ebx, ebx
0x180006493  mov     eax, 80004005h
0x180006498  mov     r8d, 96h
0x18000649e  cmovns  ebx, eax
0x1800064a1  mov     r9d, ebx
0x1800064a4  jmp     loc_1800065A9
0x1800064a9  mov     rbx, [rbp+Str]
0x1800064ad  mov     edx, 5Ch ; '\'; Ch
0x1800064b2  mov     rcx, rbx; Str
0x1800064b5  call    cs:__imp_wcschr
0x1800064bb  mov     rdx, rbx; unsigned __int16 *
0x1800064be  test    rax, rax
0x1800064c1  jz      short loc_1800064E0
0x1800064c3  lea     rcx, [rbp+var_30]; unsigned __int16 **
0x1800064c7  call    ?SdpStrExpand@@YAJPEAPEAGPEBG@Z; SdpStrExpand(ushort * *,ushort const *)
0x1800064cc  mov     ebx, eax
0x1800064ce  test    eax, eax
0x1800064d0  jns     short loc_180006500
0x1800064d2  mov     r9d, eax
0x1800064d5  mov     r8d, 9Eh
0x1800064db  jmp     loc_1800065A9
0x1800064e0  lea     r8, [rbp+var_30]; unsigned __int16 **
0x1800064e4  mov     rcx, r15; unsigned __int16 *
0x1800064e7  call    ?SdpBuildPath@@YAJPEBG0PEAPEAG@Z; SdpBuildPath(ushort const *,ushort const *,ushort * *)
0x1800064ec  mov     ebx, eax
0x1800064ee  test    eax, eax
0x1800064f0  jns     short loc_180006500
0x1800064f2  mov     r9d, eax
0x1800064f5  mov     r8d, 0A2h
0x1800064fb  jmp     loc_1800065A9
0x180006500  mov     edx, [rbp+arg_18]; unsigned int
0x180006503  lea     r8, [rbp+var_10]; unsigned __int16 **
0x180006507  mov     rcx, [rbp+var_30]; unsigned __int16 *
0x18000650b  call    ?SdpLoadString@@YAJPEBGKPEAPEAG@Z; SdpLoadString(ushort const *,ulong,ushort * *)
0x180006510  mov     ebx, eax
0x180006512  test    eax, eax
0x180006514  jns     short loc_180006539
0x180006516  mov     r9d, eax; int
0x180006519  lea     rdx, aSdplocalizedis; "SdpLocalizeDisplayInformation"
0x180006520  mov     r8d, 0A7h; int
0x180006526  mov     ecx, 1; Level
0x18000652b  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180006530  mov     r14, [rbp+var_10]
0x180006534  jmp     loc_1800065BA
0x180006539  mov     r14, [rbp+var_10]
0x18000653d  mov     rcx, [rdi]; bstrString
0x180006540  test    rcx, rcx
0x180006543  jz      short loc_180006552
0x180006545  call    cs:__imp_SysFreeString
0x18000654b  mov     qword ptr [rdi], 0
0x180006552  mov     rcx, [rbp+psz]; psz
0x180006556  call    cs:__imp_SysAllocString
0x18000655c  mov     [rdi], rax
0x18000655f  test    rax, rax
0x180006562  jnz     short loc_18000656C
0x180006564  mov     r8d, 0B0h
0x18000656a  jmp     short loc_1800065A0
0x18000656c  test    r14, r14
0x18000656f  jz      short loc_1800065BA
0x180006571  mov     rcx, [rdi+8]; bstrString
0x180006575  test    rcx, rcx
0x180006578  jz      short loc_180006588
0x18000657a  call    cs:__imp_SysFreeString
0x180006580  mov     qword ptr [rdi+8], 0
0x180006588  mov     rcx, r14; psz
0x18000658b  call    cs:__imp_SysAllocString
0x180006591  mov     [rdi+8], rax
0x180006595  test    rax, rax
0x180006598  jnz     short loc_1800065BA
0x18000659a  mov     r8d, 0B5h; int
0x1800065a0  mov     r9d, 8007000Eh; int
0x1800065a6  mov     ebx, r9d
0x1800065a9  lea     rdx, aSdplocalizedis; "SdpLocalizeDisplayInformation"
0x1800065b0  mov     ecx, 1; Level
0x1800065b5  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x1800065ba  cmp     [rbp+psz], 0
0x1800065bf  jz      short loc_1800065CA
0x1800065c1  mov     rcx, [rbp+psz]; Block
0x1800065c5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800065ca  test    r14, r14
0x1800065cd  jz      short loc_1800065D7
0x1800065cf  mov     rcx, r14; Block
  ... truncated ...
```
