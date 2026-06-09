# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x180018fb4`
- end: `0x1800191f4`
- name: `?_Forced_rehash@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z`
- size: `576`
- prototype: `void __fastcall(__int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800183f8`

## callees

- `0x180016b28`
- `0x180018b40`
- `0x180018fb4`
- `0x18001997c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180018ff8`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180018ff8`

## pseudocode

```c
void __fastcall std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Forced_rehash(
        __int64 a1,
        unsigned __int64 a2)
{
  unsigned __int64 v2; // rcx
  __int64 v3; // rbp
  unsigned __int64 v4; // rcx
  __int64 v5; // rbx
  __int64 v6; // rcx
  _QWORD *v7; // rbx
  _QWORD *v8; // rdi
  const wchar_t **v9; // r15
  const wchar_t *v10; // r8
  __int64 v11; // r10
  unsigned __int64 v12; // rdx
  __int64 i; // r14
  __int64 v14; // rax
  __int64 v15; // r12
  __int64 v16; // r14
  _QWORD *v17; // rsi
  const wchar_t *v18; // rdx
  const wchar_t *v19; // rcx
  _QWORD *v20; // r8
  _QWORD *v21; // rdx
  _QWORD *v22; // rcx
  _QWORD *v23; // rax
  _QWORD *v24; // r8
  const wchar_t *v25; // rdx
  size_t v26; // r8
  const wchar_t *v27; // rcx
  _QWORD *v28; // r8
  _QWORD *v29; // rdx
  _QWORD *v30; // rcx
  _QWORD *v31; // rax
  _QWORD *v32; // rdx
  _QWORD *v33; // rax
  _QWORD *v34; // rcx
  unsigned __int64 *v35; // [rsp+50h] [rbp+8h] BYREF

  HIDWORD(v35) = HIDWORD(a1);
  LODWORD(v35) = 0;
  _BitScanReverse64(&v2, 0xFFFFFFFFFFFFFFFuLL);
  if ( a2 > 1LL << v2 )
    std::_Xlength_error("invalid hash bucket count");
  v3 = qword_180035148;
  LODWORD(v35) = 0;
  _BitScanReverse64(&v4, (a2 - 1) | 1);
  v5 = 1LL << ((unsigned __int8)v4 + 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,bool (*)(void)>>>>>>::_Assign_grow(
    (__int64)&qword_180035158,
    2 * v5,
    qword_180035148);
  v6 = v5 - 1;
  qword_180035178 = v5;
  qword_180035170 = v5 - 1;
  v7 = *(_QWORD **)qword_180035148;
  v8 = *(_QWORD **)qword_180035148;
  while ( v7 != (_QWORD *)v3 )
  {
    v8 = (_QWORD *)*v8;
    v9 = (const wchar_t **)(v7 + 2);
    v10 = (const wchar_t *)(v7 + 2);
    v11 = v7[4];
    if ( v7[5] > 7u )
      v10 = *v9;
    v12 = 0;
    for ( i = 0xCBF29CE484222325uLL; v12 < 2 * v11; i = 0x100000001B3LL * (v14 ^ i) )
      v14 = *((unsigned __int8 *)v10 + v12++);
    v15 = qword_180035158;
    v16 = 2 * (v6 & i);
    if ( *(_QWORD *)(qword_180035158 + 8 * v16) == v3 )
    {
      *(_QWORD *)(qword_180035158 + 8 * v16) = v7;
LABEL_11:
      *(_QWORD *)(v15 + 8 * v16 + 8) = v7;
      goto LABEL_32;
    }
    v17 = *(_QWORD **)(qword_180035158 + 8 * v16 + 8);
    v18 = (const wchar_t *)(v17 + 2);
    if ( v17[5] > 7u )
      v18 = *(const wchar_t **)v18;
    v19 = (const wchar_t *)(v7 + 2);
    if ( v7[5] > 7u )
      v19 = *v9;
    if ( v11 == v17[4] && (!v11 || !wmemcmp(v19, v18, v7[4])) )
    {
      v20 = (_QWORD *)*v17;
      if ( (_QWORD *)*v17 != v7 )
      {
        v21 = (_QWORD *)v7[1];
        *v21 = v8;
        v22 = (_QWORD *)v8[1];
        *v22 = v20;
        v23 = (_QWORD *)v20[1];
        *v23 = v7;
        v20[1] = v22;
        v8[1] = v21;
        v7[1] = v23;
      }
      goto LABEL_11;
    }
    while ( 1 )
    {
      v24 = v17 + 1;
      if ( *(_QWORD **)(v15 + 8 * v16) == v17 )
        break;
      v17 = (_QWORD *)*v24;
      v25 = (const wchar_t *)(*v24 + 16LL);
      if ( *(_QWORD *)(*v24 + 40LL) > 7u )
        v25 = *(const wchar_t **)v25;
      v26 = v7[4];
      if ( v7[5] <= 7u )
        v27 = (const wchar_t *)(v7 + 2);
      else
        v27 = *v9;
      if ( v26 == v17[4] && (!v26 || !wmemcmp(v27, v25, v26)) )
      {
        v28 = (_QWORD *)*v17;
        v29 = (_QWORD *)v7[1];
        *v29 = v8;
        v30 = (_QWORD *)v8[1];
        *v30 = v28;
        v31 = (_QWORD *)v28[1];
        *v31 = v7;
        v28[1] = v30;
        v8[1] = v29;
        v7[1] = v31;
        goto LABEL_32;
      }
    }
    v32 = (_QWORD *)v7[1];
    *v32 = v8;
    v33 = (_QWORD *)v8[1];
    *v33 = v17;
    v34 = (_QWORD *)*v24;
    *v34 = v7;
    *v24 = v33;
    v8[1] = v32;
    v7[1] = v34;
    *(_QWORD *)(v15 + 8 * v16) = v7;
LABEL_32:
    v6 = qword_180035170;
    v7 = v8;
  }
  v35 = 0;
  std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Clear_guard::~_Clear_guard(&v35);
}

```

## disassembly

```asm
0x180018fb4  mov     rax, rsp
0x180018fb7  mov     [rax+10h], rbx
0x180018fbb  mov     [rax+18h], rbp
0x180018fbf  mov     [rax+8], rcx
0x180018fc3  push    rsi
0x180018fc4  push    rdi
0x180018fc5  push    r12
0x180018fc7  push    r14
0x180018fc9  push    r15
0x180018fcb  sub     rsp, 20h
0x180018fcf  mov     dword ptr [rax+8], 0
0x180018fd6  mov     rax, 0FFFFFFFFFFFFFFFh
0x180018fe0  bsr     rcx, rax
0x180018fe4  mov     eax, 1
0x180018fe9  shl     rax, cl
0x180018fec  cmp     rdx, rax
0x180018fef  jbe     short loc_180018FFF
0x180018ff1  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x180018ff8  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180018fff  mov     rbp, cs:qword_180035148
0x180019006  lea     rax, [rdx-1]
0x18001900a  or      rax, 1
0x18001900e  mov     dword ptr [rsp+48h+arg_0], 0
0x180019016  bsr     rcx, rax
0x18001901a  mov     ebx, 1
0x18001901f  mov     r8, rbp
0x180019022  inc     ecx
0x180019024  shl     rbx, cl
0x180019027  lea     rcx, qword_180035158
0x18001902e  lea     rdx, [rbx+rbx]
0x180019032  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@P6A_NXZ@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@P6A_NXZ@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,bool (*)(void)>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,bool (*)(void)>>>>)
0x180019037  lea     rcx, [rbx-1]
0x18001903b  mov     cs:qword_180035178, rbx
0x180019042  mov     rbx, cs:qword_180035148
0x180019049  mov     cs:qword_180035170, rcx
0x180019050  mov     rbx, [rbx]
0x180019053  mov     rdi, rbx
0x180019056  cmp     rbx, rbp
0x180019059  jz      loc_1800191CA
0x18001905f  mov     rdi, [rdi]
0x180019062  lea     r15, [rbx+10h]
0x180019066  cmp     qword ptr [r15+18h], 7
0x18001906b  mov     r8, r15
0x18001906e  mov     r10, [r15+10h]
0x180019072  jbe     short loc_180019077
0x180019074  mov     r8, [r15]
0x180019077  lea     r9, [r10+r10]
0x18001907b  xor     edx, edx
0x18001907d  mov     r14, 0CBF29CE484222325h
0x180019087  test    r9, r9
0x18001908a  jz      short loc_1800190AA
0x18001908c  movzx   eax, byte ptr [r8+rdx]
0x180019091  mov     r11, 100000001B3h
0x18001909b  xor     r14, rax
0x18001909e  inc     rdx
0x1800190a1  imul    r14, r11
0x1800190a5  cmp     rdx, r9
0x1800190a8  jb      short loc_18001908C
0x1800190aa  mov     r12, cs:qword_180035158
0x1800190b1  and     r14, rcx
0x1800190b4  add     r14, r14
0x1800190b7  cmp     [r12+r14*8], rbp
0x1800190bb  jnz     short loc_1800190CB
0x1800190bd  mov     [r12+r14*8], rbx
0x1800190c1  mov     [r12+r14*8+8], rbx
0x1800190c6  jmp     loc_1800191BB
0x1800190cb  mov     rsi, [r12+r14*8+8]
0x1800190d0  lea     rdx, [rsi+10h]
0x1800190d4  cmp     qword ptr [rdx+18h], 7
0x1800190d9  mov     rax, [rdx+10h]
0x1800190dd  jbe     short loc_1800190E2
0x1800190df  mov     rdx, [rdx]; S2
0x1800190e2  cmp     qword ptr [r15+18h], 7
0x1800190e7  mov     rcx, r15
0x1800190ea  jbe     short loc_1800190EF
0x1800190ec  mov     rcx, [r15]; S1
0x1800190ef  cmp     r10, rax
0x1800190f2  jnz     short loc_180019130
0x1800190f4  test    r10, r10
0x1800190f7  jz      short loc_180019105
0x1800190f9  mov     r8, r10; N
0x1800190fc  call    wmemcmp
0x180019101  test    eax, eax
0x180019103  jnz     short loc_180019130
0x180019105  mov     r8, [rsi]
0x180019108  cmp     r8, rbx
0x18001910b  jz      short loc_1800190C1
0x18001910d  mov     rdx, [rbx+8]
0x180019111  mov     [rdx], rdi
0x180019114  mov     rcx, [rdi+8]
0x180019118  mov     [rcx], r8
0x18001911b  mov     rax, [r8+8]
0x18001911f  mov     [rax], rbx
0x180019122  mov     [r8+8], rcx
0x180019126  mov     [rdi+8], rdx
0x18001912a  mov     [rbx+8], rax
0x18001912e  jmp     short loc_1800190C1
0x180019130  lea     r8, [rsi+8]
0x180019134  cmp     [r12+r14*8], rsi
0x180019138  jz      short loc_180019198
0x18001913a  mov     rsi, [r8]
0x18001913d  cmp     qword ptr [rsi+28h], 7
0x180019142  lea     rdx, [rsi+10h]
0x180019146  jbe     short loc_18001914B
0x180019148  mov     rdx, [rdx]; S2
0x18001914b  cmp     qword ptr [r15+18h], 7
0x180019150  mov     r8, [r15+10h]; N
0x180019154  jbe     short loc_18001915B
0x180019156  mov     rcx, [r15]
0x180019159  jmp     short loc_18001915E
0x18001915b  mov     rcx, r15; S1
0x18001915e  cmp     r8, [rsi+20h]
0x180019162  jnz     short loc_180019130
0x180019164  test    r8, r8
0x180019167  jz      short loc_180019172
0x180019169  call    wmemcmp
0x18001916e  test    eax, eax
0x180019170  jnz     short loc_180019130
0x180019172  mov     r8, [rsi]
0x180019175  mov     rdx, [rbx+8]
0x180019179  mov     [rdx], rdi
0x18001917c  mov     rcx, [rdi+8]
0x180019180  mov     [rcx], r8
0x180019183  mov     rax, [r8+8]
0x180019187  mov     [rax], rbx
0x18001918a  mov     [r8+8], rcx
0x18001918e  mov     [rdi+8], rdx
0x180019192  mov     [rbx+8], rax
0x180019196  jmp     short loc_1800191BB
0x180019198  mov     rdx, [rbx+8]
0x18001919c  mov     [rdx], rdi
0x18001919f  mov     rax, [rdi+8]
0x1800191a3  mov     [rax], rsi
0x1800191a6  mov     rcx, [r8]
0x1800191a9  mov     [rcx], rbx
0x1800191ac  mov     [r8], rax
0x1800191af  mov     [rdi+8], rdx
0x1800191b3  mov     [rbx+8], rcx
0x1800191b7  mov     [r12+r14*8], rbx
0x1800191bb  mov     rcx, cs:qword_180035170
0x1800191c2  mov     rbx, rdi
0x1800191c5  jmp     loc_180019056
0x1800191ca  lea     rcx, [rsp+48h+arg_0]
0x1800191cf  mov     [rsp+48h+arg_0], 0
0x1800191d8  call    ??1_Clear_guard@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Clear_guard::~_Clear_guard(void)
0x1800191dd  mov     rbx, [rsp+48h+arg_8]
0x1800191e2  mov     rbp, [rsp+48h+arg_10]
0x1800191e7  add     rsp, 20h
0x1800191eb  pop     r15
0x1800191ed  pop     r14
0x1800191ef  pop     r12
0x1800191f1  pop     rdi
0x1800191f2  pop     rsi
0x1800191f3  retn
```
