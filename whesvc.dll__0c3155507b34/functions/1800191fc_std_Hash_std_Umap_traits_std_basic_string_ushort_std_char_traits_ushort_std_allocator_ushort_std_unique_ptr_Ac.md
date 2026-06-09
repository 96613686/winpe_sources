# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::unique_ptr<ActionPlugin,std::default_delete<ActionPlugin>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::unique_ptr<ActionPlugin,std::default_delete<ActionPlugin>>>>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x1800191fc`
- end: `0x180019416`
- name: `?_Forced_rehash@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VActionPlugin@@U?$default_delete@VActionPlugin@@@std@@@2@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z`
- size: `538`
- prototype: `int __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800181b4`

## callees

- `0x180016b28`
- `0x1800191fc`
- `0x18001997c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001923a`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001923a`

## pseudocode

```c
int __fastcall std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<ActionPlugin>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<ActionPlugin>>>,0>>::_Forced_rehash(
        _QWORD *a1,
        unsigned __int64 a2)
{
  unsigned __int64 v3; // rcx
  unsigned __int64 v4; // rbp
  unsigned __int64 v5; // rcx
  __int64 *v6; // rsi
  __int64 v7; // rbx
  unsigned __int64 v8; // rax
  _QWORD *v9; // rbx
  _QWORD *v10; // rdi
  const wchar_t **v11; // r15
  const wchar_t *v12; // r8
  _QWORD *v13; // r10
  unsigned __int64 v14; // rdx
  __int64 i; // rcx
  __int64 v16; // r12
  __int64 v17; // r14
  _QWORD *v18; // rsi
  const wchar_t *v19; // rdx
  const wchar_t *v20; // rcx
  _QWORD *v21; // r8
  _QWORD *v22; // rdx
  _QWORD *v23; // rcx
  unsigned __int64 *v24; // r8
  const wchar_t *v25; // rdx
  size_t v26; // r8
  const wchar_t *v27; // rcx
  _QWORD *v28; // r8
  _QWORD *v29; // rdx
  _QWORD *v30; // rcx
  _QWORD *v31; // rdx
  _QWORD *v32; // rcx

  _BitScanReverse64(&v3, 0xFFFFFFFFFFFFFFFuLL);
  if ( a2 > 1LL << v3 )
    std::_Xlength_error("invalid hash bucket count");
  v4 = a1[1];
  _BitScanReverse64(&v5, (a2 - 1) | 1);
  v6 = a1 + 3;
  v7 = 1LL << ((unsigned __int8)v5 + 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,bool (*)(void)>>>>>>::_Assign_grow(
    (__int64)(a1 + 3),
    2 * v7,
    v4);
  LODWORD(v8) = v7 - 1;
  a1[7] = v7;
  a1[6] = v7 - 1;
  v9 = *(_QWORD **)a1[1];
  v10 = v9;
  while ( v9 != (_QWORD *)v4 )
  {
    v10 = (_QWORD *)*v10;
    v11 = (const wchar_t **)(v9 + 2);
    v12 = (const wchar_t *)(v9 + 2);
    v13 = (_QWORD *)v9[4];
    if ( v9[5] > 7u )
      v12 = *v11;
    v14 = 0;
    for ( i = 0xCBF29CE484222325uLL; v14 < 2 * (__int64)v13; i = 0x100000001B3LL * (v8 ^ i) )
      v8 = *((unsigned __int8 *)v12 + v14++);
    v16 = *v6;
    v17 = 2 * (i & a1[6]);
    if ( *(_QWORD *)(*v6 + 16 * (i & a1[6])) == v4 )
    {
      *(_QWORD *)(v16 + 16 * (i & a1[6])) = v9;
      *(_QWORD *)(v16 + 8 * v17 + 8) = v9;
    }
    else
    {
      v18 = *(_QWORD **)(v16 + 16 * (i & a1[6]) + 8);
      v19 = (const wchar_t *)(v18 + 2);
      v8 = v18[4];
      if ( v18[5] > 7u )
        v19 = *(const wchar_t **)v19;
      v20 = (const wchar_t *)(v9 + 2);
      if ( v9[5] > 7u )
        v20 = *v11;
      if ( v13 != (_QWORD *)v8 || v13 && (LODWORD(v8) = wmemcmp(v20, v19, v9[4]), (_DWORD)v8) )
      {
        while ( 1 )
        {
          v24 = v18 + 1;
          if ( *(_QWORD **)(v16 + 8 * v17) == v18 )
            break;
          v18 = (_QWORD *)*v24;
          v25 = (const wchar_t *)(*v24 + 16);
          if ( *(_QWORD *)(*v24 + 40) > 7u )
            v25 = *(const wchar_t **)v25;
          v26 = v9[4];
          if ( v9[5] <= 7u )
            v27 = (const wchar_t *)(v9 + 2);
          else
            v27 = *v11;
          if ( v26 == v18[4] && (!v26 || !wmemcmp(v27, v25, v26)) )
          {
            v28 = (_QWORD *)*v18;
            v29 = (_QWORD *)v9[1];
            *v29 = v10;
            v30 = (_QWORD *)v10[1];
            *v30 = v28;
            v8 = v28[1];
            *(_QWORD *)v8 = v9;
            v28[1] = v30;
            v10[1] = v29;
            v9[1] = v8;
            goto LABEL_32;
          }
        }
        v31 = (_QWORD *)v9[1];
        *v31 = v10;
        v8 = v10[1];
        *(_QWORD *)v8 = v18;
        v32 = (_QWORD *)*v24;
        *v32 = v9;
        *v24 = v8;
        v10[1] = v31;
        v9[1] = v32;
        *(_QWORD *)(v16 + 8 * v17) = v9;
      }
      else
      {
        v21 = (_QWORD *)*v18;
        if ( (_QWORD *)*v18 != v9 )
        {
          v22 = (_QWORD *)v9[1];
          *v22 = v10;
          v23 = (_QWORD *)v10[1];
          *v23 = v21;
          v8 = v21[1];
          *(_QWORD *)v8 = v9;
          v21[1] = v23;
          v10[1] = v22;
          v9[1] = v8;
        }
        *(_QWORD *)(v16 + 8 * v17 + 8) = v9;
      }
LABEL_32:
      v6 = a1 + 3;
    }
    v9 = v10;
  }
  return v8;
}

```

## disassembly

```asm
0x1800191fc  push    rbx
0x1800191fe  push    rbp
0x1800191ff  push    rsi
0x180019200  push    rdi
0x180019201  push    r12
0x180019203  push    r13
0x180019205  push    r14
0x180019207  push    r15
0x180019209  sub     rsp, 28h
0x18001920d  mov     rax, 0FFFFFFFFFFFFFFFh
0x180019217  mov     [rsp+68h+arg_8], 0
0x18001921f  mov     r13, rcx
0x180019222  bsr     rcx, rax
0x180019226  mov     eax, 1
0x18001922b  shl     rax, cl
0x18001922e  cmp     rdx, rax
0x180019231  jbe     short loc_180019241
0x180019233  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x18001923a  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180019241  mov     rbp, [r13+8]
0x180019245  lea     rax, [rdx-1]
0x180019249  or      rax, 1
0x18001924d  mov     [rsp+68h+arg_8], 0
0x180019255  bsr     rcx, rax
0x180019259  mov     ebx, 1
0x18001925e  lea     rsi, [r13+18h]
0x180019262  inc     ecx
0x180019264  mov     r8, rbp
0x180019267  shl     rbx, cl
0x18001926a  mov     rcx, rsi
0x18001926d  lea     rdx, [rbx+rbx]
0x180019271  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@P6A_NXZ@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@P6A_NXZ@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,bool (*)(void)>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,bool (*)(void)>>>>)
0x180019276  lea     rax, [rbx-1]
0x18001927a  mov     [r13+38h], rbx
0x18001927e  mov     [r13+30h], rax
0x180019282  mov     rbx, [r13+8]
0x180019286  mov     rbx, [rbx]
0x180019289  mov     rdi, rbx
0x18001928c  cmp     rbx, rbp
0x18001928f  jz      loc_180019405
0x180019295  mov     rdi, [rdi]
0x180019298  lea     r15, [rbx+10h]
0x18001929c  cmp     qword ptr [r15+18h], 7
0x1800192a1  mov     r8, r15
0x1800192a4  mov     r10, [r15+10h]
0x1800192a8  jbe     short loc_1800192AD
0x1800192aa  mov     r8, [r15]
0x1800192ad  lea     r9, [r10+r10]
0x1800192b1  xor     edx, edx
0x1800192b3  mov     rcx, 0CBF29CE484222325h
0x1800192bd  test    r9, r9
0x1800192c0  jz      short loc_1800192E0
0x1800192c2  movzx   eax, byte ptr [r8+rdx]
0x1800192c7  mov     r11, 100000001B3h
0x1800192d1  xor     rcx, rax
0x1800192d4  inc     rdx
0x1800192d7  imul    rcx, r11
0x1800192db  cmp     rdx, r9
0x1800192de  jb      short loc_1800192C2
0x1800192e0  mov     r14, [r13+30h]
0x1800192e4  mov     r12, [rsi]
0x1800192e7  and     r14, rcx
0x1800192ea  add     r14, r14
0x1800192ed  cmp     [r12+r14*8], rbp
0x1800192f1  jnz     short loc_180019301
0x1800192f3  mov     [r12+r14*8], rbx
0x1800192f7  mov     [r12+r14*8+8], rbx
0x1800192fc  jmp     loc_1800193FD
0x180019301  mov     rsi, [r12+r14*8+8]
0x180019306  lea     rdx, [rsi+10h]
0x18001930a  cmp     qword ptr [rdx+18h], 7
0x18001930f  mov     rax, [rdx+10h]
0x180019313  jbe     short loc_180019318
0x180019315  mov     rdx, [rdx]; S2
0x180019318  cmp     qword ptr [r15+18h], 7
0x18001931d  mov     rcx, r15
0x180019320  jbe     short loc_180019325
0x180019322  mov     rcx, [r15]; S1
0x180019325  cmp     r10, rax
0x180019328  jnz     short loc_18001936E
0x18001932a  test    r10, r10
0x18001932d  jz      short loc_18001933B
0x18001932f  mov     r8, r10; N
0x180019332  call    wmemcmp
0x180019337  test    eax, eax
0x180019339  jnz     short loc_18001936E
0x18001933b  mov     r8, [rsi]
0x18001933e  cmp     r8, rbx
0x180019341  jz      short loc_180019364
0x180019343  mov     rdx, [rbx+8]
0x180019347  mov     [rdx], rdi
0x18001934a  mov     rcx, [rdi+8]
0x18001934e  mov     [rcx], r8
0x180019351  mov     rax, [r8+8]
0x180019355  mov     [rax], rbx
0x180019358  mov     [r8+8], rcx
0x18001935c  mov     [rdi+8], rdx
0x180019360  mov     [rbx+8], rax
0x180019364  mov     [r12+r14*8+8], rbx
0x180019369  jmp     loc_1800193F9
0x18001936e  lea     r8, [rsi+8]
0x180019372  cmp     [r12+r14*8], rsi
0x180019376  jz      short loc_1800193D6
0x180019378  mov     rsi, [r8]
0x18001937b  cmp     qword ptr [rsi+28h], 7
0x180019380  lea     rdx, [rsi+10h]
0x180019384  jbe     short loc_180019389
0x180019386  mov     rdx, [rdx]; S2
0x180019389  cmp     qword ptr [r15+18h], 7
0x18001938e  mov     r8, [r15+10h]; N
0x180019392  jbe     short loc_180019399
0x180019394  mov     rcx, [r15]
0x180019397  jmp     short loc_18001939C
0x180019399  mov     rcx, r15; S1
0x18001939c  cmp     r8, [rsi+20h]
0x1800193a0  jnz     short loc_18001936E
0x1800193a2  test    r8, r8
0x1800193a5  jz      short loc_1800193B0
0x1800193a7  call    wmemcmp
0x1800193ac  test    eax, eax
0x1800193ae  jnz     short loc_18001936E
0x1800193b0  mov     r8, [rsi]
0x1800193b3  mov     rdx, [rbx+8]
0x1800193b7  mov     [rdx], rdi
0x1800193ba  mov     rcx, [rdi+8]
0x1800193be  mov     [rcx], r8
0x1800193c1  mov     rax, [r8+8]
0x1800193c5  mov     [rax], rbx
0x1800193c8  mov     [r8+8], rcx
0x1800193cc  mov     [rdi+8], rdx
0x1800193d0  mov     [rbx+8], rax
0x1800193d4  jmp     short loc_1800193F9
0x1800193d6  mov     rdx, [rbx+8]
0x1800193da  mov     [rdx], rdi
0x1800193dd  mov     rax, [rdi+8]
0x1800193e1  mov     [rax], rsi
0x1800193e4  mov     rcx, [r8]
0x1800193e7  mov     [rcx], rbx
0x1800193ea  mov     [r8], rax
0x1800193ed  mov     [rdi+8], rdx
0x1800193f1  mov     [rbx+8], rcx
0x1800193f5  mov     [r12+r14*8], rbx
0x1800193f9  lea     rsi, [r13+18h]
0x1800193fd  mov     rbx, rdi
0x180019400  jmp     loc_18001928C
0x180019405  add     rsp, 28h
0x180019409  pop     r15
0x18001940b  pop     r14
0x18001940d  pop     r13
0x18001940f  pop     r12
0x180019411  pop     rdi
0x180019412  pop     rsi
0x180019413  pop     rbp
0x180019414  pop     rbx
0x180019415  retn
```
