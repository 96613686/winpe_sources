# ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>>::SetAt(ushort const *,ushort const *)

- ea: `0x140007098`
- end: `0x140007382`
- name: `?SetAt@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V12@V?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAPEAU__POSITION@@PEBG0@Z`
- size: `746`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14000660c`
- `0x140077dac`
- `0x140079e5c`
- `0x14007cc80`

## callees

- `0x140007020`
- `0x140007098`
- `0x140008e0c`
- `0x140015230`
- `0x1400364dc`
- `0x1400396dc`
- `0x140046c32`
- `0x14009ad10`
- `0x14009ad1c`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x140007173`
- `KERNEL32!CompareStringW` at `0x140007173`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400071ec`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140007230`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400071ec`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140007230`
- `USER32!CharUpperW` at `0x1400070d2`
- `USER32!CharUpperW` at `0x1400070d2`

## pseudocode

```c
__int64 __fastcall ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::SetAt(
        __int64 a1,
        const WCHAR *a2,
        char *a3)
{
  char *v3; // r15
  unsigned int v6; // r13d
  WCHAR v7; // ax
  const WCHAR *v8; // rbx
  __int64 v9; // rbx
  __int64 i; // r14
  _QWORD *v11; // rsi
  _BYTE *v12; // r13
  unsigned __int64 v13; // r12
  __int64 v14; // rdi
  unsigned __int64 v15; // rdx
  _BYTE *v16; // rcx
  _QWORD *v18; // rsi
  _BYTE *v19; // r13
  unsigned __int64 v20; // r12
  __int64 v21; // r8
  __int64 v22; // rdi
  unsigned __int64 v23; // rdx
  _BYTE *v24; // rcx
  __int64 v25; // rax
  __int64 *v26; // rdx
  __int64 v27; // [rsp+0h] [rbp-68h] BYREF
  unsigned int v28; // [rsp+78h] [rbp+10h]
  char *v29; // [rsp+80h] [rbp+18h]

  v29 = a3;
  v3 = a3;
  if ( !a2 )
    ATL::AtlThrowImpl(-2147467259);
  v6 = 0;
  v7 = *a2;
  if ( *a2 )
  {
    v8 = a2;
    do
    {
      v6 = (unsigned __int16)CharUpperW((LPWSTR)v7) + 33 * v6;
      v7 = *++v8;
    }
    while ( *v8 );
    v3 = v29;
  }
  v28 = v6 % *(_DWORD *)(a1 + 16);
  v9 = -1;
  if ( *(_QWORD *)a1 )
  {
    for ( i = *(_QWORD *)(*(_QWORD *)a1 + 8LL * (v6 % *(_DWORD *)(a1 + 16))); ; i = *(_QWORD *)(i + 16) )
    {
      if ( !i )
        goto LABEL_12;
      if ( *(_DWORD *)(i + 24) == v6 && CompareStringW(0x7Fu, 1u, *(PCNZWCH *)i, -1, a2, -1) == 2 )
        break;
    }
    v11 = (_QWORD *)(i + 8);
    if ( !v3 )
      goto LABEL_28;
    do
      ++v9;
    while ( *(_WORD *)&v3[2 * v9] );
    if ( !(_DWORD)v9 )
    {
LABEL_28:
      ATL::CSimpleStringT<unsigned short,0>::Empty(i + 8);
      return i;
    }
    v12 = (_BYTE *)*v11;
    v13 = *(unsigned int *)(*v11 - 16LL);
    if ( (int)((*(_DWORD *)(*v11 - 12LL) - v9) | (1 - *(_DWORD *)(*v11 - 8LL))) < 0 )
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(i + 8, (unsigned int)v9);
    v14 = 2LL * (int)v9;
    if ( v14 )
    {
      v15 = (v3 - v12) >> 1;
      v16 = (_BYTE *)*v11;
      if ( v15 <= v13 )
      {
        if ( !v16 )
          goto LABEL_24;
        v15 = (unsigned __int64)&v16[2 * v15];
        if ( !v15 )
          goto LABEL_24;
        memmove_0(v16, (const void *)v15, 2LL * (int)v9);
      }
      else
      {
        if ( !v16 )
        {
LABEL_24:
          *(_DWORD *)_o__errno(v16, v15, a3) = 22;
          invalid_parameter_noinfo();
          goto LABEL_25;
        }
        memcpy_0(v16, v3, 2LL * (int)v9);
      }
    }
LABEL_25:
    if ( (int)v9 < 0 || (int)v9 > *(_DWORD *)(*v11 - 12LL) )
      ATL::AtlThrowImpl(-2147024809);
    *(_DWORD *)(*v11 - 16LL) = v9;
    *(_WORD *)(v14 + *v11) = 0;
    return i;
  }
LABEL_12:
  if ( !*(_QWORD *)a1 )
  {
    LOBYTE(a3) = 1;
    if ( !(unsigned __int8)ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>>::InitHashTable(
                             a1,
                             *(unsigned int *)(a1 + 16),
                             a3) )
      ATL::AtlThrowImpl(-2147024882);
  }
  v25 = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::NewNode(
          a1,
          a2,
          v28,
          v6);
  i = v25;
  v18 = (_QWORD *)(v25 + 8);
  if ( !v3 )
    goto LABEL_47;
  do
    ++v9;
  while ( *(_WORD *)&v3[2 * v9] );
  if ( !(_DWORD)v9 )
  {
LABEL_47:
    ATL::CSimpleStringT<unsigned short,0>::Empty(v18);
    return i;
  }
  v19 = (_BYTE *)*v18;
  v20 = *(unsigned int *)(*v18 - 16LL);
  if ( (int)((*(_DWORD *)(*v18 - 12LL) - v9) | (1 - *(_DWORD *)(*v18 - 8LL))) < 0 )
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(v18, (unsigned int)v9);
  v22 = 2LL * (int)v9;
  if ( v22 )
  {
    v23 = (v3 - v19) >> 1;
    v24 = (_BYTE *)*v18;
    if ( v23 <= v20 )
    {
      if ( v24 )
      {
        v23 = (unsigned __int64)&v24[2 * v23];
        if ( v23 )
        {
          memmove_0(v24, (const void *)v23, 2LL * (int)v9);
          goto LABEL_30;
        }
      }
    }
    else if ( v24 )
    {
      memcpy_0(v24, v3, 2LL * (int)v9);
      goto LABEL_30;
    }
    *(_DWORD *)_o__errno(v24, v23, v21) = 22;
    invalid_parameter_noinfo();
  }
LABEL_30:
  if ( (int)v9 < 0 )
    goto LABEL_57;
  while ( (int)v9 > *(_DWORD *)(*v18 - 12LL) )
  {
LABEL_57:
    try
    {
      ATL::AtlThrowImpl(-2147024809);
    }
    catch ( ... )
    {
      v26 = &v27;
      ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::RemoveAtPos(
        v26[14],
        v26[15]);
      throw;
    }
  }
  *(_DWORD *)(*v18 - 16LL) = v9;
  *(_WORD *)(v22 + *v18) = 0;
  return i;
}

```

## disassembly

```asm
0x140007098  mov     [rsp+arg_10], r8
0x14000709d  mov     [rsp+arg_0], rcx
0x1400070a2  push    rbx
0x1400070a3  push    rsi
0x1400070a4  push    rdi
0x1400070a5  push    r12
0x1400070a7  push    r13
0x1400070a9  push    r14
0x1400070ab  push    r15
0x1400070ad  sub     rsp, 30h
0x1400070b1  mov     r15, r8
0x1400070b4  mov     r12, rdx
0x1400070b7  mov     rsi, rcx
0x1400070ba  xor     ecx, ecx
0x1400070bc  test    rdx, rdx
0x1400070bf  jz      short loc_140007128
0x1400070c1  mov     r13d, ecx
0x1400070c4  movzx   eax, word ptr [rdx]
0x1400070c7  test    ax, ax
0x1400070ca  jz      short loc_1400070F8
0x1400070cc  mov     rbx, rdx
0x1400070cf  movzx   ecx, ax; lpsz
0x1400070d2  call    cs:__imp_CharUpperW
0x1400070d8  movzx   ecx, ax
0x1400070db  imul    r13d, 21h ; '!'
0x1400070df  add     r13d, ecx
0x1400070e2  lea     rbx, [rbx+2]
0x1400070e6  movzx   eax, word ptr [rbx]
0x1400070e9  test    ax, ax
0x1400070ec  jnz     short loc_1400070CF
0x1400070ee  mov     r15, [rsp+68h+arg_10]
0x1400070f6  xor     ecx, ecx
0x1400070f8  xor     edx, edx
0x1400070fa  mov     eax, r13d
0x1400070fd  div     dword ptr [rsi+10h]
0x140007100  mov     dword ptr [rsp+68h+arg_8], edx
0x140007104  mov     r14, [rsi]
0x140007107  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000710b  lea     edi, [rbx+2]
0x14000710e  test    r14, r14
0x140007111  jz      short loc_140007133
0x140007113  mov     r14, [r14+rdx*8]
0x140007117  test    r14, r14
0x14000711a  jz      short loc_140007133
0x14000711c  cmp     [r14+18h], r13d
0x140007120  jz      short loc_14000715D
0x140007122  mov     r14, [r14+10h]
0x140007126  jmp     short loc_140007117
0x140007128  mov     ecx, 80004005h; int
0x14000712d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140007133  cmp     [rsi], rcx
0x140007136  jnz     loc_140007356
0x14000713c  mov     r8b, dil
0x14000713f  mov     edx, [rsi+10h]
0x140007142  mov     rcx, rsi
0x140007145  call    ?InitHashTable@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V12@V?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V3@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>>::InitHashTable(uint,bool)
0x14000714a  test    al, al
0x14000714c  jnz     loc_140007356
0x140007152  mov     ecx, 8007000Eh; int
0x140007157  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14000715d  mov     [rsp+68h+cchCount2], ebx; cchCount2
0x140007161  mov     [rsp+68h+lpString2], r12; lpString2
0x140007166  mov     r9d, ebx; cchCount1
0x140007169  mov     r8, [r14]; lpString1
0x14000716c  mov     edx, edi; dwCmpFlags
0x14000716e  mov     ecx, 7Fh; Locale
0x140007173  call    cs:__imp_CompareStringW
0x140007179  cmp     eax, 2
0x14000717c  jnz     loc_14000721F
0x140007182  lea     rsi, [r14+8]
0x140007186  xor     eax, eax
0x140007188  test    r15, r15
0x14000718b  jz      loc_140007226
0x140007191  inc     rbx
0x140007194  cmp     [r15+rbx*2], ax
0x140007199  jnz     short loc_140007191
0x14000719b  test    ebx, ebx
0x14000719d  jz      loc_140007226
0x1400071a3  mov     r13, [rsi]
0x1400071a6  mov     r12d, [r13-10h]
0x1400071aa  sub     edi, [r13-8]
0x1400071ae  mov     eax, [r13-0Ch]
0x1400071b2  sub     eax, ebx
0x1400071b4  or      edi, eax
0x1400071b6  jge     short loc_1400071C2
0x1400071b8  mov     edx, ebx
0x1400071ba  mov     rcx, rsi
0x1400071bd  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1400071c2  movsxd  rax, ebx
0x1400071c5  lea     rdi, [rax+rax]
0x1400071c9  test    rdi, rdi
0x1400071cc  jz      short loc_1400071FD
0x1400071ce  mov     rdx, r15
0x1400071d1  sub     rdx, r13
0x1400071d4  sar     rdx, 1
0x1400071d7  mov     rcx, [rsi]; void *
0x1400071da  cmp     rdx, r12
0x1400071dd  jbe     loc_140007286
0x1400071e3  test    rcx, rcx
0x1400071e6  jnz     loc_140007276
0x1400071ec  call    cs:__imp__o__errno
0x1400071f2  mov     dword ptr [rax], 16h
0x1400071f8  call    _invalid_parameter_noinfo
0x1400071fd  test    ebx, ebx
0x1400071ff  js      loc_14000734B
0x140007205  mov     rax, [rsi]
0x140007208  cmp     ebx, [rax-0Ch]
0x14000720b  jg      loc_14000734B
0x140007211  mov     [rax-10h], ebx
0x140007214  mov     rcx, [rsi]
0x140007217  xor     eax, eax
0x140007219  mov     [rdi+rcx], ax
0x14000721d  jmp     short loc_140007263
0x14000721f  xor     ecx, ecx
0x140007221  jmp     loc_140007122
0x140007226  mov     rcx, rsi
0x140007229  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x14000722e  jmp     short loc_140007263
0x140007230  call    cs:__imp__o__errno
0x140007236  mov     dword ptr [rax], 16h
0x14000723c  call    _invalid_parameter_noinfo
0x140007241  xor     r15d, r15d
0x140007244  test    ebx, ebx
0x140007246  js      loc_140007376
0x14000724c  mov     rax, [rsi]
0x14000724f  cmp     ebx, [rax-0Ch]
0x140007252  jg      loc_140007376
0x140007258  mov     [rax-10h], ebx
0x14000725b  mov     rcx, [rsi]
0x14000725e  mov     [rdi+rcx], r15w
0x140007263  mov     rax, r14
0x140007266  add     rsp, 30h
0x14000726a  pop     r15
0x14000726c  pop     r14
0x14000726e  pop     r13
0x140007270  pop     r12
0x140007272  pop     rdi
0x140007273  pop     rsi
0x140007274  pop     rbx
0x140007275  retn
0x140007276  mov     r8, rdi; Size
0x140007279  mov     rdx, r15; Src
0x14000727c  call    memcpy_0
0x140007281  jmp     loc_1400071FD
0x140007286  test    rcx, rcx
0x140007289  jz      loc_1400071EC
0x14000728f  lea     rdx, [rcx+rdx*2]; Src
0x140007293  test    rdx, rdx
0x140007296  jz      loc_1400071EC
0x14000729c  mov     r8, rdi; Size
0x14000729f  call    memmove_0
0x1400072a4  jmp     loc_1400071FD
0x1400072a9  lea     rsi, [rax+8]
0x1400072ad  xor     eax, eax
0x1400072af  test    r15, r15
0x1400072b2  jz      short loc_14000731B
0x1400072b4  inc     rbx
0x1400072b7  cmp     [r15+rbx*2], ax
0x1400072bc  jnz     short loc_1400072B4
0x1400072be  test    ebx, ebx
0x1400072c0  jz      short loc_14000731B
0x1400072c2  mov     r13, [rsi]
0x1400072c5  mov     r12d, [r13-10h]
0x1400072c9  sub     edi, [r13-8]
0x1400072cd  mov     eax, [r13-0Ch]
0x1400072d1  sub     eax, ebx
0x1400072d3  or      edi, eax
0x1400072d5  jge     short loc_1400072E1
0x1400072d7  mov     edx, ebx
0x1400072d9  mov     rcx, rsi
0x1400072dc  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1400072e1  movsxd  rax, ebx
0x1400072e4  lea     rdi, [rax+rax]
0x1400072e8  test    rdi, rdi
0x1400072eb  jz      loc_140007241
0x1400072f1  mov     rdx, r15
0x1400072f4  sub     rdx, r13
0x1400072f7  sar     rdx, 1
0x1400072fa  mov     rcx, [rsi]; void *
0x1400072fd  cmp     rdx, r12
0x140007300  jbe     short loc_140007328
0x140007302  test    rcx, rcx
0x140007305  jz      loc_140007230
0x14000730b  mov     r8, rdi; Size
0x14000730e  mov     rdx, r15; Src
0x140007311  call    memcpy_0
0x140007316  jmp     loc_140007241
0x14000731b  mov     rcx, rsi
0x14000731e  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x140007323  jmp     loc_140007263
0x140007328  test    rcx, rcx
0x14000732b  jz      loc_140007230
0x140007331  lea     rdx, [rcx+rdx*2]; Src
0x140007335  test    rdx, rdx
0x140007338  jz      loc_140007230
0x14000733e  mov     r8, rdi; Size
0x140007341  call    memmove_0
0x140007346  jmp     loc_140007241
0x14000734b  mov     ecx, 80070057h; int
0x140007350  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140007356  mov     r9d, r13d
0x140007359  mov     r8d, dword ptr [rsp+68h+arg_8]
0x14000735e  mov     rdx, r12
0x140007361  mov     rcx, rsi
0x140007364  call    ?NewNode@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V12@V?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@@ATL@@AEAAPEAVCNode@12@PEBGII@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>>::NewNode(ushort const *,uint,uint)
0x140007369  mov     r14, rax
0x14000736c  mov     [rsp+68h+arg_8], rax
0x140007371  jmp     loc_1400072A9
0x140007376  mov     ecx, 80070057h; int
0x14000737b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
