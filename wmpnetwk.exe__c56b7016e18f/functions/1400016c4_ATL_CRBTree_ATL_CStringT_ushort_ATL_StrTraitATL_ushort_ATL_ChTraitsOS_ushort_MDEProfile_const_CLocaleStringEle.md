# ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,MDEProfile const *,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<MDEProfile const *>>::RBInsert(ushort const *,MDEProfile const * const &)

- ea: `0x1400016c4`
- end: `0x140001ac0`
- name: `?RBInsert@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@PEBUMDEProfile@@V?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@PEBUMDEProfile@@@2@@ATL@@IEAAPEAVCNode@12@PEBGAEBQEBUMDEProfile@@@Z`
- size: `1020`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140001b88`
- `0x14001bef0`

## callees

- `0x1400016c4`
- `0x140001ac8`
- `0x140001b28`
- `0x140006d70`
- `0x1400396dc`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x14000178b`
- `KERNEL32!CompareStringW` at `0x1400017ce`
- `KERNEL32!CompareStringW` at `0x14000178b`
- `KERNEL32!CompareStringW` at `0x1400017ce`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140001970`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140001a31`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140001970`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140001a31`

## pseudocode

```c
PCNZWCH *__fastcall ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,MDEProfile const *,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<MDEProfile const *>>::RBInsert(
        PCNZWCH **a1,
        char *a2,
        const WCHAR **a3)
{
  PCNZWCH *v6; // rdi
  __int64 v7; // r8
  const WCHAR *v8; // rax
  PCNZWCH **v9; // r15
  PCNZWCH *v10; // rsi
  PCNZWCH *j; // r14
  PCNZWCH **v12; // r14
  PCNZWCH *v13; // rax
  PCNZWCH *v14; // r9
  PCNZWCH v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rax
  PCNZWCH *v26; // rcx
  __int64 v27; // rcx
  PCNZWCH *v28; // rax
  PCNZWCH *v29; // rcx
  PCNZWCH *v30; // rdx
  PCNZWCH *i; // r8
  PCNZWCH *v32; // rax
  PCNZWCH *v33; // rax
  const WCHAR *v34; // rcx

  if ( a1[2] )
    goto LABEL_2;
  if ( !a1[5] )
  {
    v32 = (PCNZWCH *)malloc(0x30u);
    a1[5] = v32;
    if ( !v32 )
      ATL::AtlThrowImpl(-2147024882);
    *(_OWORD *)v32 = 0;
    *((_OWORD *)v32 + 1) = 0;
    *((_OWORD *)v32 + 2) = 0;
    *((_DWORD *)a1[5] + 4) = 1;
    a1[5][4] = (PCNZWCH)a1[5];
    v33 = a1[5];
    v34 = v33[4];
    v33[3] = v34;
    a1[5][5] = v34;
    *a1 = a1[5];
  }
  v26 = a1[4];
  if ( v26 )
  {
    if ( 0xFFFFFFFFFFFFFFFFuLL / (unsigned __int64)v26 < 0x30 )
      goto LABEL_63;
    v27 = 48LL * (_QWORD)v26;
  }
  else
  {
    v27 = 0;
  }
  v28 = (PCNZWCH *)malloc(v27 + 8);
  if ( !v28 )
LABEL_63:
    ATL::AtlThrowImpl(-2147024882);
  v29 = a1[3];
  a1[3] = v28;
  v30 = a1[4];
  *v28 = (PCNZWCH)v29;
  for ( i = &v28[6 * (_QWORD)v30 - 5]; ; i -= 6 )
  {
    v30 = (PCNZWCH *)((char *)v30 - 1);
    if ( (__int64)v30 < 0 )
      break;
    i[3] = (PCNZWCH)a1[2];
    a1[2] = i;
  }
LABEL_2:
  v6 = a1[2];
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    (void **)v6,
    a2);
  v8 = *a3;
  v9 = (PCNZWCH **)(v6 + 5);
  *((_DWORD *)v6 + 4) = 1;
  v6[1] = v8;
  v6[5] = 0;
  a1[2] = (PCNZWCH *)a1[2][3];
  *((_DWORD *)v6 + 4) = 0;
  if ( v6 == (PCNZWCH *)-24LL )
    goto LABEL_3;
  v6[3] = (PCNZWCH)a1[5];
  if ( v6 == (PCNZWCH *)-32LL )
    goto LABEL_3;
  v6[4] = (PCNZWCH)a1[5];
  if ( v6 == (PCNZWCH *)-40LL )
    goto LABEL_3;
  v10 = 0;
  *v9 = a1[5];
  a1[1] = (PCNZWCH *)((char *)a1[1] + 1);
  for ( j = *a1; j != a1[5]; j = *v12 )
  {
    v10 = j;
    if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)a2, -1, *j, -1) == 3 )
      v12 = (PCNZWCH **)(j + 4);
    else
      v12 = (PCNZWCH **)(j + 3);
  }
  *v9 = v10;
  if ( v10 )
  {
    if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)a2, -1, *v10, -1) == 3 )
      v10[4] = (PCNZWCH)v6;
    else
      v10[3] = (PCNZWCH)v6;
  }
  else
  {
    *a1 = v6;
  }
  *((_DWORD *)v6 + 4) = 0;
  v13 = *a1;
  if ( v6 != *a1 )
  {
    v14 = v6;
    do
    {
      v15 = v14[5];
      if ( *((_DWORD *)v15 + 4) )
        break;
      v16 = *((_QWORD *)v15 + 5);
      v17 = *(_QWORD *)(v16 + 24);
      if ( v15 == (PCNZWCH)v17 )
      {
        v17 = *(_QWORD *)(v16 + 32);
        if ( !v17 || *(_DWORD *)(v17 + 16) )
        {
          if ( v14 == *((PCNZWCH **)v15 + 4) )
            ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,MDEProfile const *,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<MDEProfile const *>>::LeftRotate(
              a1,
              v15,
              v7,
              v14[5]);
          *((_DWORD *)v14[5] + 4) = 1;
          *(_DWORD *)(*((_QWORD *)v14[5] + 5) + 16LL) = 0;
          ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,MDEProfile const *,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<MDEProfile const *>>::RightRotate(
            a1,
            *((_QWORD *)v14[5] + 5));
          goto LABEL_21;
        }
      }
      else if ( !v17 || *(_DWORD *)(v17 + 16) )
      {
        v19 = *((_QWORD *)v15 + 3);
        if ( v14 == (PCNZWCH *)v19 )
        {
          v14 = (PCNZWCH *)v14[5];
          if ( v15 )
          {
            *((_QWORD *)v15 + 3) = *(_QWORD *)(v19 + 32);
            v20 = *(_QWORD *)(v19 + 32);
            if ( (PCNZWCH *)v20 != a1[5] )
              *(_QWORD *)(v20 + 40) = v15;
            *(_QWORD *)(v19 + 40) = *((_QWORD *)v15 + 5);
            v21 = *((_QWORD *)v15 + 5);
            if ( (PCNZWCH *)v21 == a1[5] )
            {
              *a1 = (PCNZWCH *)v19;
            }
            else if ( v15 == *(PCNZWCH *)(v21 + 32) )
            {
              *(_QWORD *)(v21 + 32) = v19;
            }
            else
            {
              *(_QWORD *)(v21 + 24) = v19;
            }
            *(_QWORD *)(v19 + 32) = v15;
            *((_QWORD *)v15 + 5) = v19;
          }
        }
        *((_DWORD *)v14[5] + 4) = 1;
        *(_DWORD *)(*((_QWORD *)v14[5] + 5) + 16LL) = 0;
        v22 = *((_QWORD *)v14[5] + 5);
        if ( v22 )
        {
          v23 = *(_QWORD *)(v22 + 32);
          *(_QWORD *)(v22 + 32) = *(_QWORD *)(v23 + 24);
          v24 = *(_QWORD *)(v23 + 24);
          if ( (PCNZWCH *)v24 != a1[5] )
            *(_QWORD *)(v24 + 40) = v22;
          *(_QWORD *)(v23 + 40) = *(_QWORD *)(v22 + 40);
          v25 = *(_QWORD *)(v22 + 40);
          if ( (PCNZWCH *)v25 == a1[5] )
          {
            *a1 = (PCNZWCH *)v23;
          }
          else if ( v22 == *(_QWORD *)(v25 + 24) )
          {
            *(_QWORD *)(v25 + 24) = v23;
          }
          else
          {
            *(_QWORD *)(v25 + 32) = v23;
          }
          *(_QWORD *)(v23 + 24) = v22;
          *(_QWORD *)(v22 + 40) = v23;
        }
        goto LABEL_21;
      }
      *((_DWORD *)v15 + 4) = 1;
      *(_DWORD *)(v17 + 16) = 1;
      *(_DWORD *)(*((_QWORD *)v14[5] + 5) + 16LL) = 0;
      v14 = (PCNZWCH *)*((_QWORD *)v14[5] + 5);
LABEL_21:
      v13 = *a1;
    }
    while ( v14 != *a1 );
  }
  *((_DWORD *)v13 + 4) = 1;
  if ( *a1 == (PCNZWCH *)-40LL )
LABEL_3:
    ATL::AtlThrowImpl(-2147467259);
  (*a1)[5] = (PCNZWCH)a1[5];
  return v6;
}

```

## disassembly

```asm
0x1400016c4  push    rbx
0x1400016c6  push    rbp
0x1400016c7  push    rsi
0x1400016c8  push    rdi
0x1400016c9  push    r12
0x1400016cb  push    r13
0x1400016cd  push    r14
0x1400016cf  push    r15
0x1400016d1  sub     rsp, 38h
0x1400016d5  xor     r12d, r12d
0x1400016d8  mov     rsi, r8
0x1400016db  mov     rbp, rdx
0x1400016de  mov     rbx, rcx
0x1400016e1  mov     r13d, 1
0x1400016e7  cmp     [rcx+10h], r12
0x1400016eb  jz      loc_14000193A
0x1400016f1  mov     rdi, [rbx+10h]
0x1400016f5  mov     rdx, rbp
0x1400016f8  mov     rcx, rdi
0x1400016fb  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x140001700  mov     rax, [rsi]
0x140001703  lea     r15, [rdi+28h]
0x140001707  mov     [rdi+10h], r13d
0x14000170b  mov     [rdi+8], rax
0x14000170f  mov     [r15], r12
0x140001712  mov     rax, [rbx+10h]
0x140001716  mov     rcx, [rax+18h]
0x14000171a  mov     [rbx+10h], rcx
0x14000171e  lea     rcx, [rdi+18h]
0x140001722  mov     [rdi+10h], r12d
0x140001726  test    rcx, rcx
0x140001729  jnz     short loc_140001736
0x14000172b  mov     ecx, 80004005h; int
0x140001730  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140001736  mov     rax, [rbx+28h]
0x14000173a  mov     [rcx], rax
0x14000173d  lea     rcx, [rdi+20h]
0x140001741  test    rcx, rcx
0x140001744  jz      short loc_14000172B
0x140001746  mov     rax, [rbx+28h]
0x14000174a  mov     [rcx], rax
0x14000174d  test    r15, r15
0x140001750  jz      short loc_14000172B
0x140001752  mov     rax, [rbx+28h]
0x140001756  mov     rsi, r12
0x140001759  mov     [r15], rax
0x14000175c  add     [rbx+8], r13
0x140001760  mov     r14, [rbx]
0x140001763  cmp     r14, [rbx+28h]
0x140001767  jz      short loc_1400017A3
0x140001769  mov     rax, [r14]
0x14000176c  or      r9d, 0FFFFFFFFh; cchCount1
0x140001770  mov     [rsp+78h+cchCount2], 0FFFFFFFFh; cchCount2
0x140001778  mov     r8, rbp; lpString1
0x14000177b  mov     edx, r13d; dwCmpFlags
0x14000177e  mov     [rsp+78h+lpString2], rax; lpString2
0x140001783  mov     ecx, 7Fh; Locale
0x140001788  mov     rsi, r14
0x14000178b  call    cs:__imp_CompareStringW
0x140001791  sub     eax, r13d
0x140001794  jnz     loc_140001A9C
0x14000179a  add     r14, 18h
0x14000179e  mov     r14, [r14]
0x1400017a1  jmp     short loc_140001763
0x1400017a3  mov     [r15], rsi
0x1400017a6  test    rsi, rsi
0x1400017a9  jz      loc_140001A24
0x1400017af  mov     rax, [rsi]
0x1400017b2  or      r9d, 0FFFFFFFFh; cchCount1
0x1400017b6  mov     [rsp+78h+cchCount2], 0FFFFFFFFh; cchCount2
0x1400017be  mov     r8, rbp; lpString1
0x1400017c1  mov     edx, r13d; dwCmpFlags
0x1400017c4  mov     [rsp+78h+lpString2], rax; lpString2
0x1400017c9  mov     ecx, 7Fh; Locale
0x1400017ce  call    cs:__imp_CompareStringW
0x1400017d4  sub     eax, r13d
0x1400017d7  jnz     loc_140001AAE
0x1400017dd  mov     [rsi+18h], rdi
0x1400017e1  mov     [rdi+10h], r12d
0x1400017e5  mov     rax, [rbx]
0x1400017e8  cmp     rdi, rax
0x1400017eb  jz      short loc_140001842
0x1400017ed  mov     r9, rdi
0x1400017f0  mov     rdx, [r9+28h]
0x1400017f4  cmp     [rdx+10h], r12d
0x1400017f8  jnz     short loc_140001842
0x1400017fa  mov     rcx, [rdx+28h]
0x1400017fe  mov     rax, [rcx+18h]
0x140001802  cmp     rdx, rax
0x140001805  jnz     short loc_14000186E
0x140001807  mov     rax, [rcx+20h]
0x14000180b  test    rax, rax
0x14000180e  jz      loc_1400019CA
0x140001814  cmp     [rax+10h], r12d
0x140001818  jnz     loc_1400019CA
0x14000181e  mov     [rdx+10h], r13d
0x140001822  mov     [rax+10h], r13d
0x140001826  mov     rax, [r9+28h]
0x14000182a  mov     rcx, [rax+28h]
0x14000182e  mov     [rcx+10h], r12d
0x140001832  mov     rax, [r9+28h]
0x140001836  mov     r9, [rax+28h]
0x14000183a  mov     rax, [rbx]
0x14000183d  cmp     r9, rax
0x140001840  jnz     short loc_1400017F0
0x140001842  mov     [rax+10h], r13d
0x140001846  mov     rax, [rbx]
0x140001849  add     rax, 28h ; '('
0x14000184d  jz      loc_14000172B
0x140001853  mov     rcx, [rbx+28h]
0x140001857  mov     [rax], rcx
0x14000185a  mov     rax, rdi
0x14000185d  add     rsp, 38h
0x140001861  pop     r15
0x140001863  pop     r14
0x140001865  pop     r13
0x140001867  pop     r12
0x140001869  pop     rdi
0x14000186a  pop     rsi
0x14000186b  pop     rbp
0x14000186c  pop     rbx
0x14000186d  retn
0x14000186e  test    rax, rax
0x140001871  jnz     loc_140001A04
0x140001877  mov     rcx, [rdx+18h]
0x14000187b  cmp     r9, rcx
0x14000187e  jnz     short loc_1400018CA
0x140001880  mov     r9, rdx
0x140001883  test    rdx, rdx
0x140001886  jz      short loc_1400018CA
0x140001888  mov     rax, [rcx+20h]
0x14000188c  mov     [rdx+18h], rax
0x140001890  mov     rax, [rcx+20h]
0x140001894  cmp     rax, [rbx+28h]
0x140001898  jz      short loc_14000189E
0x14000189a  mov     [rax+28h], rdx
0x14000189e  mov     rax, [rdx+28h]
0x1400018a2  mov     [rcx+28h], rax
0x1400018a6  mov     rax, [rdx+28h]
0x1400018aa  cmp     rax, [rbx+28h]
0x1400018ae  jz      loc_140001A13
0x1400018b4  cmp     rdx, [rax+20h]
0x1400018b8  jnz     loc_140001A1B
0x1400018be  mov     [rax+20h], rcx
0x1400018c2  mov     [rcx+20h], rdx
0x1400018c6  mov     [rdx+28h], rcx
0x1400018ca  mov     rax, [r9+28h]
0x1400018ce  mov     [rax+10h], r13d
0x1400018d2  mov     rax, [r9+28h]
0x1400018d6  mov     rcx, [rax+28h]
0x1400018da  mov     [rcx+10h], r12d
0x1400018de  mov     rax, [r9+28h]
0x1400018e2  mov     rcx, [rax+28h]
0x1400018e6  test    rcx, rcx
0x1400018e9  jz      loc_14000183A
0x1400018ef  mov     rdx, [rcx+20h]
0x1400018f3  mov     rax, [rdx+18h]
0x1400018f7  mov     [rcx+20h], rax
0x1400018fb  mov     rax, [rdx+18h]
0x1400018ff  cmp     rax, [rbx+28h]
0x140001903  jz      short loc_140001909
0x140001905  mov     [rax+28h], rcx
0x140001909  mov     rax, [rcx+28h]
0x14000190d  mov     [rdx+28h], rax
0x140001911  mov     rax, [rcx+28h]
0x140001915  cmp     rax, [rbx+28h]
0x140001919  jz      loc_1400019B9
0x14000191f  cmp     rcx, [rax+18h]
0x140001923  jnz     loc_1400019C1
0x140001929  mov     [rax+18h], rdx
0x14000192d  mov     [rdx+18h], rcx
0x140001931  mov     [rcx+28h], rdx
0x140001935  jmp     loc_14000183A
0x14000193a  cmp     [rcx+28h], r12
0x14000193e  jz      loc_140001A2C
0x140001944  mov     rcx, [rbx+20h]
0x140001948  test    rcx, rcx
0x14000194b  jz      loc_140001A89
0x140001951  xor     edx, edx
0x140001953  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001957  div     rcx
0x14000195a  cmp     rax, 30h ; '0'
0x14000195e  jb      loc_140001A91
0x140001964  lea     rcx, [rcx+rcx*2]
0x140001968  shl     rcx, 4
0x14000196c  add     rcx, 8; Size
0x140001970  call    cs:__imp_malloc
0x140001976  test    rax, rax
0x140001979  jz      loc_140001A91
0x14000197f  mov     rcx, [rbx+18h]
0x140001983  mov     [rbx+18h], rax
0x140001987  mov     rdx, [rbx+20h]
0x14000198b  mov     [rax], rcx
0x14000198e  lea     r8, [rdx+rdx*2]
0x140001992  shl     r8, 4
0x140001996  add     r8, 0FFFFFFFFFFFFFFD8h
0x14000199a  add     r8, rax
0x14000199d  jmp     short loc_1400019AF
0x14000199f  mov     rax, [rbx+10h]
0x1400019a3  mov     [r8+18h], rax
0x1400019a7  mov     [rbx+10h], r8
0x1400019ab  sub     r8, 30h ; '0'
0x1400019af  sub     rdx, r13
0x1400019b2  jns     short loc_14000199F
0x1400019b4  jmp     loc_1400016F1
0x1400019b9  mov     [rbx], rdx
0x1400019bc  jmp     loc_14000192D
0x1400019c1  mov     [rax+20h], rdx
0x1400019c5  jmp     loc_14000192D
0x1400019ca  cmp     r9, [rdx+20h]
0x1400019ce  jnz     short loc_1400019DB
0x1400019d0  mov     rcx, rbx
0x1400019d3  mov     r9, rdx
0x1400019d6  call    ?LeftRotate@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@PEBUMDEProfile@@V?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@PEBUMDEProfile@@@2@@ATL@@AEAAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,MDEProfile const *,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<MDEProfile const *>>::LeftRotate(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,MDEProfile const *,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<MDEProfile const *>>::CNode *)
0x1400019db  mov     rax, [r9+28h]
0x1400019df  mov     [rax+10h], r13d
0x1400019e3  mov     rax, [r9+28h]
0x1400019e7  mov     rcx, [rax+28h]
0x1400019eb  mov     [rcx+10h], r12d
0x1400019ef  mov     rcx, rbx
0x1400019f2  mov     rdx, [r9+28h]
0x1400019f6  mov     rdx, [rdx+28h]
0x1400019fa  call    ?RightRotate@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@PEBUMDEProfile@@V?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@PEBUMDEProfile@@@2@@ATL@@AEAAPEAVCNode@12@PEAV312@@Z; ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,MDEProfile const *,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<MDEProfile const *>>::RightRotate(ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,MDEProfile const *,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<MDEProfile const *>>::CNode *)
0x1400019ff  jmp     loc_14000183A
0x140001a04  cmp     [rax+10h], r12d
0x140001a08  jnz     loc_140001877
0x140001a0e  jmp     loc_14000181E
0x140001a13  mov     [rbx], rcx
0x140001a16  jmp     loc_1400018C2
0x140001a1b  mov     [rax+18h], rcx
0x140001a1f  jmp     loc_1400018C2
0x140001a24  mov     [rbx], rdi
0x140001a27  jmp     loc_1400017E1
0x140001a2c  mov     ecx, 30h ; '0'; Size
0x140001a31  call    cs:__imp_malloc
0x140001a37  mov     [rbx+28h], rax
0x140001a3b  test    rax, rax
0x140001a3e  jnz     short loc_140001A4B
0x140001a40  mov     ecx, 8007000Eh; int
0x140001a45  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140001a4b  xorps   xmm0, xmm0
0x140001a4e  movups  xmmword ptr [rax], xmm0
0x140001a51  movups  xmmword ptr [rax+10h], xmm0
0x140001a55  movups  xmmword ptr [rax+20h], xmm0
0x140001a59  mov     rax, [rbx+28h]
0x140001a5d  mov     [rax+10h], r13d
0x140001a61  mov     rax, [rbx+28h]
0x140001a65  mov     [rax+20h], rax
0x140001a69  mov     rax, [rbx+28h]
0x140001a6d  mov     rcx, [rax+20h]
0x140001a71  mov     [rax+18h], rcx
0x140001a75  mov     rax, [rbx+28h]
0x140001a79  mov     [rax+28h], rcx
0x140001a7d  mov     rax, [rbx+28h]
0x140001a81  mov     [rbx], rax
0x140001a84  jmp     loc_140001944
0x140001a89  mov     rcx, r12
0x140001a8c  jmp     loc_14000196C
0x140001a91  mov     ecx, 8007000Eh; int
0x140001a96  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140001a9c  cmp     eax, 2
0x140001a9f  jnz     loc_14000179A
0x140001aa5  add     r14, 20h ; ' '
0x140001aa9  jmp     loc_14000179E
0x140001aae  cmp     eax, 2
0x140001ab1  jnz     loc_1400017DD
0x140001ab7  mov     [rsi+20h], rdi
0x140001abb  jmp     loc_1400017E1
```
