# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>::emplace<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>> const &>(std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>> const &)

- ea: `0x1800183f8`
- end: `0x18001865c`
- name: `??$emplace@AEBU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@_N@1@AEBU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@1@@Z`
- size: `612`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001cb0`

## callees

- `0x180003be4`
- `0x180003d44`
- `0x18001806c`
- `0x1800183f8`
- `0x180018664`
- `0x180018fb4`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180018496`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180018496`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::emplace<std::pair<std::wstring const,std::wstring> const &>(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v5; // r8
  _QWORD *v6; // rdx
  __int64 v7; // rbp
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // r8
  _QWORD *v10; // rdi
  __int64 v11; // r9
  unsigned __int64 v12; // rcx
  float v13; // xmm0_4
  unsigned __int64 v14; // rbx
  float v15; // xmm2_4
  float v16; // xmm0_4
  unsigned __int64 v17; // rcx
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rdx
  _QWORD *v22; // r8
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // r9
  __int128 v27; // [rsp+20h] [rbp-38h] BYREF
  __int64 *v28; // [rsp+30h] [rbp-28h] BYREF
  _QWORD *v29; // [rsp+38h] [rbp-20h]

  v5 = a3[2];
  if ( a3[3] <= 7u )
    v6 = a3;
  else
    v6 = (_QWORD *)*a3;
  v7 = 0xCBF29CE484222325uLL;
  v8 = 0;
  v9 = 2 * v5;
  if ( v9 )
  {
    do
      v7 = 0x100000001B3LL * (*((unsigned __int8 *)v6 + v8++) ^ (unsigned __int64)v7);
    while ( v8 < v9 );
  }
  std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_last<std::wstring>(
    v8,
    &v27,
    (__int64)a3,
    v7);
  if ( !*((_QWORD *)&v27 + 1) )
  {
    if ( qword_180035150 == 0x333333333333333LL )
      std::_Xlength_error("unordered_map/set too long");
    v28 = &qword_180035148;
    v29 = 0;
    v10 = operator new(0x50u);
    v29 = v10;
    std::wstring::wstring(v10 + 2, a3);
    std::wstring::wstring(v10 + 6, a3 + 4);
    v11 = qword_180035150;
    v12 = qword_180035150 + 1;
    if ( qword_180035150 + 1 < 0 )
      v13 = (float)(int)(v12 & 1 | (v12 >> 1)) + (float)(int)(v12 & 1 | (v12 >> 1));
    else
      v13 = (float)(int)v12;
    v14 = qword_180035178;
    if ( qword_180035178 < 0 )
      v15 = (float)(qword_180035178 & 1 | (unsigned int)((unsigned __int64)qword_180035178 >> 1))
          + (float)(qword_180035178 & 1 | (unsigned int)((unsigned __int64)qword_180035178 >> 1));
    else
      v15 = (float)(int)qword_180035178;
    if ( (float)(v13 / v15) > *(float *)&ActionToDllMapping )
    {
      v16 = o_ceilf_0(v13 / *(float *)&ActionToDllMapping);
      v17 = 0;
      if ( v16 >= 9.223372e18 )
      {
        v16 = v16 - 9.223372e18;
        if ( v16 < 9.223372e18 )
          v17 = 0x8000000000000000uLL;
      }
      v18 = v17 + (unsigned int)(int)v16;
      v19 = 8;
      if ( v18 > 8 )
        v19 = v18;
      if ( v14 < v19 )
      {
        if ( v14 >= 0x200 || (v14 *= 8LL, v14 < v19) )
          v14 = v19;
      }
      std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Forced_rehash(
        v19,
        v14);
      v27 = *(_OWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_last<std::wstring>(
                         v20,
                         &v28,
                         (__int64)(v10 + 2),
                         v7);
      v11 = qword_180035150;
    }
    v21 = v27;
    v22 = *(_QWORD **)(v27 + 8);
    qword_180035150 = v11 + 1;
    *v10 = v27;
    v10[1] = v22;
    *v22 = v10;
    *(_QWORD *)(v21 + 8) = v10;
    v23 = qword_180035158;
    v24 = 2 * (v7 & qword_180035170);
    v25 = *(_QWORD *)(qword_180035158 + 16 * (v7 & qword_180035170));
    if ( v25 == qword_180035148 )
    {
      *(_QWORD *)(qword_180035158 + 16 * (v7 & qword_180035170)) = v10;
LABEL_32:
      *(_QWORD *)(v23 + 8 * v24 + 8) = v10;
      goto LABEL_33;
    }
    if ( v25 == v21 )
    {
      *(_QWORD *)(qword_180035158 + 16 * (v7 & qword_180035170)) = v10;
    }
    else if ( *(_QWORD **)(qword_180035158 + 16 * (v7 & qword_180035170) + 8) == v22 )
    {
      goto LABEL_32;
    }
LABEL_33:
    *(_QWORD *)a2 = v10;
    *(_BYTE *)(a2 + 8) = 1;
    return a2;
  }
  *(_QWORD *)a2 = *((_QWORD *)&v27 + 1);
  *(_BYTE *)(a2 + 8) = 0;
  return a2;
}

```

## disassembly

```asm
0x1800183f8  mov     [rsp+arg_8], rbx
0x1800183fd  mov     [rsp+arg_10], rbp
0x180018402  mov     [rsp+arg_0], rcx
0x180018407  push    rsi
0x180018408  push    rdi
0x180018409  push    r14
0x18001840b  sub     rsp, 40h
0x18001840f  mov     rbx, r8
0x180018412  mov     rsi, rdx
0x180018415  mov     r8, [r8+10h]
0x180018419  cmp     qword ptr [rbx+18h], 7
0x18001841e  jbe     short loc_180018425
0x180018420  mov     rdx, [rbx]
0x180018423  jmp     short loc_180018428
0x180018425  mov     rdx, rbx
0x180018428  mov     rbp, 0CBF29CE484222325h
0x180018432  xor     ecx, ecx
0x180018434  add     r8, r8
0x180018437  jz      short loc_180018456
0x180018439  movzx   eax, byte ptr [rdx+rcx]
0x18001843d  xor     rbp, rax
0x180018440  mov     r9, 100000001B3h
0x18001844a  imul    rbp, r9
0x18001844e  inc     rcx
0x180018451  cmp     rcx, r8
0x180018454  jb      short loc_180018439
0x180018456  mov     r9, rbp
0x180018459  mov     r8, rbx
0x18001845c  lea     rdx, [rsp+58h+var_38]
0x180018461  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x180018466  mov     rax, qword ptr [rsp+58h+var_38+8]
0x18001846b  test    rax, rax
0x18001846e  jz      short loc_18001847C
0x180018470  mov     [rsi], rax
0x180018473  mov     byte ptr [rsi+8], 0
0x180018477  jmp     loc_180018646
0x18001847c  mov     rax, 333333333333333h
0x180018486  cmp     cs:qword_180035150, rax
0x18001848d  jnz     short loc_18001849D
0x18001848f  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x180018496  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001849d  lea     rax, qword_180035148
0x1800184a4  mov     [rsp+58h+var_28], rax
0x1800184a9  mov     [rsp+58h+var_20], 0
0x1800184b2  mov     ecx, 50h ; 'P'; Size
0x1800184b7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800184bc  mov     rdi, rax
0x1800184bf  mov     [rsp+58h+var_20], rax
0x1800184c4  lea     r14, [rax+10h]
0x1800184c8  mov     [rsp+58h+arg_0], r14
0x1800184cd  mov     rdx, rbx
0x1800184d0  mov     rcx, r14
0x1800184d3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800184d8  nop
0x1800184d9  lea     rdx, [rbx+20h]
0x1800184dd  lea     rcx, [r14+20h]
0x1800184e1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800184e6  nop
0x1800184e7  mov     r9, cs:qword_180035150
0x1800184ee  lea     rcx, [r9+1]
0x1800184f2  xorps   xmm0, xmm0
0x1800184f5  test    rcx, rcx
0x1800184f8  js      short loc_180018501
0x1800184fa  cvtsi2ss xmm0, rcx
0x1800184ff  jmp     short loc_180018516
0x180018501  mov     rax, rcx
0x180018504  shr     rax, 1
0x180018507  and     ecx, 1
0x18001850a  or      rax, rcx
0x18001850d  cvtsi2ss xmm0, rax
0x180018512  addss   xmm0, xmm0
0x180018516  mov     rbx, cs:qword_180035178
0x18001851d  xorps   xmm2, xmm2
0x180018520  test    rbx, rbx
0x180018523  js      short loc_18001852C
0x180018525  cvtsi2ss xmm2, rbx
0x18001852a  jmp     short loc_180018544
0x18001852c  mov     rcx, rbx
0x18001852f  shr     rcx, 1
0x180018532  mov     rax, rbx
0x180018535  and     eax, 1
0x180018538  or      rcx, rax
0x18001853b  cvtsi2ss xmm2, rcx
0x180018540  addss   xmm2, xmm2
0x180018544  movaps  xmm1, xmm0
0x180018547  divss   xmm1, xmm2
0x18001854b  movss   xmm3, cs:?ActionToDllMapping@@3V?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@B; std::unordered_map<std::wstring,std::wstring> const ActionToDllMapping
0x180018553  comiss  xmm1, xmm3
0x180018556  jbe     loc_1800185E0
0x18001855c  divss   xmm0, xmm3; X
0x180018560  call    _o_ceilf_0
0x180018565  xor     ecx, ecx
0x180018567  movss   xmm1, cs:__real@5f000000
0x18001856f  comiss  xmm0, xmm1
0x180018572  jb      short loc_18001858A
0x180018574  subss   xmm0, xmm1
0x180018578  comiss  xmm0, xmm1
0x18001857b  jnb     short loc_18001858A
0x18001857d  mov     rax, 8000000000000000h
0x180018587  mov     rcx, rax
0x18001858a  cvttss2si rax, xmm0
0x18001858f  add     rax, rcx
0x180018592  mov     ecx, 8
0x180018597  cmp     rax, rcx
0x18001859a  cmova   rcx, rax
0x18001859e  cmp     rbx, rcx
0x1800185a1  jnb     short loc_1800185B8
0x1800185a3  cmp     rbx, 200h
0x1800185aa  jnb     short loc_1800185B5
0x1800185ac  shl     rbx, 3
0x1800185b0  cmp     rbx, rcx
0x1800185b3  jnb     short loc_1800185B8
0x1800185b5  mov     rbx, rcx
0x1800185b8  mov     rdx, rbx
0x1800185bb  call    ?_Forced_rehash@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Forced_rehash(unsigned __int64)
0x1800185c0  mov     r9, rbp
0x1800185c3  mov     r8, r14
0x1800185c6  lea     rdx, [rsp+58h+var_28]
0x1800185cb  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x1800185d0  movups  xmm0, xmmword ptr [rax]
0x1800185d3  movdqu  [rsp+58h+var_38], xmm0
0x1800185d9  mov     r9, cs:qword_180035150
0x1800185e0  mov     rdx, qword ptr [rsp+58h+var_38]
0x1800185e5  mov     r8, [rdx+8]
0x1800185e9  inc     r9
0x1800185ec  mov     cs:qword_180035150, r9
0x1800185f3  mov     [rdi], rdx
0x1800185f6  mov     [rdi+8], r8
0x1800185fa  mov     [r8], rdi
0x1800185fd  mov     [rdx+8], rdi
0x180018601  mov     rcx, cs:qword_180035158
0x180018608  mov     rax, cs:qword_180035170
0x18001860f  and     rax, rbp
0x180018612  add     rax, rax
0x180018615  mov     r9, [rcx+rax*8]
0x180018619  cmp     r9, cs:qword_180035148
0x180018620  jnz     short loc_180018628
0x180018622  mov     [rcx+rax*8], rdi
0x180018626  jmp     short loc_18001863A
0x180018628  cmp     r9, rdx
0x18001862b  jnz     short loc_180018633
0x18001862d  mov     [rcx+rax*8], rdi
0x180018631  jmp     short loc_18001863F
0x180018633  cmp     [rcx+rax*8+8], r8
0x180018638  jnz     short loc_18001863F
0x18001863a  mov     [rcx+rax*8+8], rdi
0x18001863f  mov     [rsi], rdi
0x180018642  mov     byte ptr [rsi+8], 1
0x180018646  mov     rax, rsi
0x180018649  mov     rbx, [rsp+58h+arg_8]
0x18001864e  mov     rbp, [rsp+58h+arg_10]
0x180018653  add     rsp, 40h
0x180018657  pop     r14
0x180018659  pop     rdi
0x18001865a  pop     rsi
0x18001865b  retn
```
