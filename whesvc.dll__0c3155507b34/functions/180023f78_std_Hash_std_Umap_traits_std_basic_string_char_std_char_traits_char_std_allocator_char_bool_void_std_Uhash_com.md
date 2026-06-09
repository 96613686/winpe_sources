# std::_Hash<std::_Umap_traits<std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool (*)(void),std::_Uhash_compare<std::basic_string<char,std::char_traits<char>,std::allocator<char>>,std::hash<std::basic_string<char,std::char_traits<char>,std::allocator<char>>>,std::equal_to<std::basic_string<char,std::char_traits<char>,std::allocator<char>>>>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,bool (*)(void)>>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x180023f78`
- end: `0x1800241a7`
- name: `?_Forced_rehash@?$_Hash@V?$_Umap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@P6A_NXZV?$_Uhash_compare@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@P6A_NXZ@std@@@2@$0A@@std@@@std@@IEAAX_K@Z`
- size: `559`
- prototype: `void __fastcall(__int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001abc4`

## callees

- `0x180004569`
- `0x180016b28`
- `0x18001ba78`
- `0x180023f78`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180023fb7`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180023fb7`

## pseudocode

```c
void __fastcall std::_Hash<std::_Umap_traits<std::string,bool (*)(void),std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,bool (*)(void)>>,0>>::_Forced_rehash(
        __int64 a1,
        unsigned __int64 a2)
{
  unsigned __int64 v2; // rcx
  __int64 v3; // rbp
  unsigned __int64 v4; // rcx
  __int64 v5; // rbx
  __int64 v6; // r8
  _QWORD *v7; // rbx
  _QWORD *v8; // rdi
  _QWORD *v9; // r15
  _QWORD *v10; // rdx
  size_t v11; // r13
  size_t v12; // rcx
  __int64 i; // r14
  __int64 v14; // rax
  __int64 v15; // r12
  __int64 v16; // r14
  _QWORD *v17; // rsi
  _QWORD *v18; // rdx
  _QWORD *v19; // rcx
  _QWORD *v20; // r8
  _QWORD *v21; // rdx
  _QWORD *v22; // rcx
  _QWORD *v23; // rax
  _QWORD *v24; // r8
  _QWORD *v25; // rdx
  _QWORD *v26; // rcx
  _QWORD *v27; // r8
  _QWORD *v28; // rdx
  _QWORD *v29; // rcx
  _QWORD *v30; // rax
  _QWORD *v31; // rdx
  _QWORD *v32; // rax
  _QWORD *v33; // rcx
  unsigned __int64 *v34; // [rsp+70h] [rbp+8h] BYREF

  HIDWORD(v34) = HIDWORD(a1);
  LODWORD(v34) = 0;
  _BitScanReverse64(&v2, 0xFFFFFFFFFFFFFFFuLL);
  if ( a2 > 1LL << v2 )
    std::_Xlength_error("invalid hash bucket count");
  v3 = qword_180034E08;
  LODWORD(v34) = 0;
  _BitScanReverse64(&v4, (a2 - 1) | 1);
  v5 = 1LL << ((unsigned __int8)v4 + 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,bool (*)(void)>>>>>>::_Assign_grow(
    (__int64)&qword_180034E18,
    2 * v5,
    qword_180034E08);
  v6 = v5 - 1;
  qword_180034E38 = v5;
  qword_180034E30 = v5 - 1;
  v7 = *(_QWORD **)qword_180034E08;
  v8 = *(_QWORD **)qword_180034E08;
  while ( v7 != (_QWORD *)v3 )
  {
    v8 = (_QWORD *)*v8;
    v9 = v7 + 2;
    v10 = v7 + 2;
    v11 = v7[4];
    if ( v7[5] > 0xFu )
      v10 = (_QWORD *)*v9;
    v12 = 0;
    for ( i = 0xCBF29CE484222325uLL; v12 < v11; i = 0x100000001B3LL * (v14 ^ i) )
      v14 = *((unsigned __int8 *)v10 + v12++);
    v15 = qword_180034E18;
    v16 = 2 * (v6 & i);
    if ( *(_QWORD *)(qword_180034E18 + 8 * v16) == v3 )
    {
      *(_QWORD *)(qword_180034E18 + 8 * v16) = v7;
LABEL_11:
      *(_QWORD *)(v15 + 8 * v16 + 8) = v7;
      goto LABEL_32;
    }
    v17 = *(_QWORD **)(qword_180034E18 + 8 * v16 + 8);
    v18 = v17 + 2;
    if ( v17[5] > 0xFu )
      v18 = (_QWORD *)*v18;
    v19 = v7 + 2;
    if ( v7[5] > 0xFu )
      v19 = (_QWORD *)*v9;
    if ( v11 == v17[4] && (!v11 || !memcmp_0(v19, v18, v7[4])) )
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
      v25 = (_QWORD *)(*v24 + 16LL);
      if ( *(_QWORD *)(*v24 + 40LL) > 0xFu )
        v25 = (_QWORD *)*v25;
      if ( v7[5] <= 0xFu )
        v26 = v7 + 2;
      else
        v26 = (_QWORD *)*v9;
      if ( v11 == v17[4] && (!v11 || !memcmp_0(v26, v25, v11)) )
      {
        v27 = (_QWORD *)*v17;
        v28 = (_QWORD *)v7[1];
        *v28 = v8;
        v29 = (_QWORD *)v8[1];
        *v29 = v27;
        v30 = (_QWORD *)v27[1];
        *v30 = v7;
        v27[1] = v29;
        v8[1] = v28;
        v7[1] = v30;
        goto LABEL_32;
      }
    }
    v31 = (_QWORD *)v7[1];
    *v31 = v8;
    v32 = (_QWORD *)v8[1];
    *v32 = v17;
    v33 = (_QWORD *)*v24;
    *v33 = v7;
    *v24 = v32;
    v8[1] = v31;
    v7[1] = v33;
    *(_QWORD *)(v15 + 8 * v16) = v7;
LABEL_32:
    v6 = qword_180034E30;
    v7 = v8;
  }
  v34 = 0;
  std::_Hash<std::_Umap_traits<std::string,bool (*)(void),std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,bool (*)(void)>>,0>>::_Clear_guard::~_Clear_guard(&v34);
}

```

## disassembly

```asm
0x180023f78  mov     [rsp+arg_0], rcx
0x180023f7d  push    rbx
0x180023f7e  push    rbp
0x180023f7f  push    rsi
0x180023f80  push    rdi
0x180023f81  push    r12
0x180023f83  push    r13
0x180023f85  push    r14
0x180023f87  push    r15
0x180023f89  sub     rsp, 28h
0x180023f8d  mov     rax, 0FFFFFFFFFFFFFFFh
0x180023f97  mov     dword ptr [rsp+68h+arg_0], 0
0x180023f9f  bsr     rcx, rax
0x180023fa3  mov     eax, 1
0x180023fa8  shl     rax, cl
0x180023fab  cmp     rdx, rax
0x180023fae  jbe     short loc_180023FBE
0x180023fb0  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x180023fb7  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180023fbe  mov     rbp, cs:qword_180034E08
0x180023fc5  lea     rax, [rdx-1]
0x180023fc9  or      rax, 1
0x180023fcd  mov     dword ptr [rsp+68h+arg_0], 0
0x180023fd5  bsr     rcx, rax
0x180023fd9  mov     ebx, 1
0x180023fde  mov     r8, rbp
0x180023fe1  inc     ecx
0x180023fe3  shl     rbx, cl
0x180023fe6  lea     rcx, qword_180034E18
0x180023fed  lea     rdx, [rbx+rbx]
0x180023ff1  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@P6A_NXZ@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@P6A_NXZ@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,bool (*)(void)>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,bool (*)(void)>>>>)
0x180023ff6  lea     r8, [rbx-1]
0x180023ffa  mov     cs:qword_180034E38, rbx
0x180024001  mov     rbx, cs:qword_180034E08
0x180024008  mov     cs:qword_180034E30, r8
0x18002400f  mov     rbx, [rbx]
0x180024012  mov     rdi, rbx
0x180024015  cmp     rbx, rbp
0x180024018  jz      loc_180024183
0x18002401e  mov     rdi, [rdi]
0x180024021  lea     r15, [rbx+10h]
0x180024025  cmp     qword ptr [r15+18h], 0Fh
0x18002402a  mov     rdx, r15
0x18002402d  mov     r13, [r15+10h]
0x180024031  jbe     short loc_180024036
0x180024033  mov     rdx, [r15]
0x180024036  xor     ecx, ecx
0x180024038  mov     r14, 0CBF29CE484222325h
0x180024042  test    r13, r13
0x180024045  jz      short loc_180024064
0x180024047  movzx   eax, byte ptr [rdx+rcx]
0x18002404b  mov     r9, 100000001B3h
0x180024055  xor     r14, rax
0x180024058  inc     rcx
0x18002405b  imul    r14, r9
0x18002405f  cmp     rcx, r13
0x180024062  jb      short loc_180024047
0x180024064  mov     r12, cs:qword_180034E18
0x18002406b  and     r14, r8
0x18002406e  add     r14, r14
0x180024071  cmp     [r12+r14*8], rbp
0x180024075  jnz     short loc_180024085
0x180024077  mov     [r12+r14*8], rbx
0x18002407b  mov     [r12+r14*8+8], rbx
0x180024080  jmp     loc_180024174
0x180024085  mov     rsi, [r12+r14*8+8]
0x18002408a  lea     rdx, [rsi+10h]
0x18002408e  cmp     qword ptr [rdx+18h], 0Fh
0x180024093  mov     rax, [rdx+10h]
0x180024097  jbe     short loc_18002409C
0x180024099  mov     rdx, [rdx]; Buf2
0x18002409c  cmp     qword ptr [r15+18h], 0Fh
0x1800240a1  mov     rcx, r15
0x1800240a4  jbe     short loc_1800240A9
0x1800240a6  mov     rcx, [r15]; Buf1
0x1800240a9  cmp     r13, rax
0x1800240ac  jnz     short loc_1800240EA
0x1800240ae  test    r13, r13
0x1800240b1  jz      short loc_1800240BF
0x1800240b3  mov     r8, r13; Size
0x1800240b6  call    memcmp_0
0x1800240bb  test    eax, eax
0x1800240bd  jnz     short loc_1800240EA
0x1800240bf  mov     r8, [rsi]
0x1800240c2  cmp     r8, rbx
0x1800240c5  jz      short loc_18002407B
0x1800240c7  mov     rdx, [rbx+8]
0x1800240cb  mov     [rdx], rdi
0x1800240ce  mov     rcx, [rdi+8]
0x1800240d2  mov     [rcx], r8
0x1800240d5  mov     rax, [r8+8]
0x1800240d9  mov     [rax], rbx
0x1800240dc  mov     [r8+8], rcx
0x1800240e0  mov     [rdi+8], rdx
0x1800240e4  mov     [rbx+8], rax
0x1800240e8  jmp     short loc_18002407B
0x1800240ea  lea     r8, [rsi+8]
0x1800240ee  cmp     [r12+r14*8], rsi
0x1800240f2  jz      short loc_180024151
0x1800240f4  mov     rsi, [r8]
0x1800240f7  cmp     qword ptr [rsi+28h], 0Fh
0x1800240fc  lea     rdx, [rsi+10h]
0x180024100  jbe     short loc_180024105
0x180024102  mov     rdx, [rdx]; Buf2
0x180024105  cmp     qword ptr [r15+18h], 0Fh
0x18002410a  jbe     short loc_180024111
0x18002410c  mov     rcx, [r15]
0x18002410f  jmp     short loc_180024114
0x180024111  mov     rcx, r15; Buf1
0x180024114  cmp     r13, [rsi+20h]
0x180024118  jnz     short loc_1800240EA
0x18002411a  test    r13, r13
0x18002411d  jz      short loc_18002412B
0x18002411f  mov     r8, r13; Size
0x180024122  call    memcmp_0
0x180024127  test    eax, eax
0x180024129  jnz     short loc_1800240EA
0x18002412b  mov     r8, [rsi]
0x18002412e  mov     rdx, [rbx+8]
0x180024132  mov     [rdx], rdi
0x180024135  mov     rcx, [rdi+8]
0x180024139  mov     [rcx], r8
0x18002413c  mov     rax, [r8+8]
0x180024140  mov     [rax], rbx
0x180024143  mov     [r8+8], rcx
0x180024147  mov     [rdi+8], rdx
0x18002414b  mov     [rbx+8], rax
0x18002414f  jmp     short loc_180024174
0x180024151  mov     rdx, [rbx+8]
0x180024155  mov     [rdx], rdi
0x180024158  mov     rax, [rdi+8]
0x18002415c  mov     [rax], rsi
0x18002415f  mov     rcx, [r8]
0x180024162  mov     [rcx], rbx
0x180024165  mov     [r8], rax
0x180024168  mov     [rdi+8], rdx
0x18002416c  mov     [rbx+8], rcx
0x180024170  mov     [r12+r14*8], rbx
0x180024174  mov     r8, cs:qword_180034E30
0x18002417b  mov     rbx, rdi
0x18002417e  jmp     loc_180024015
0x180024183  lea     rcx, [rsp+68h+arg_0]
0x180024188  mov     [rsp+68h+arg_0], 0
0x180024191  call    ??1_Clear_guard@?$_Hash@V?$_Umap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@P6A_NXZV?$_Uhash_compare@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@P6A_NXZ@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::string,bool (*)(void),std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,bool (*)(void)>>,0>>::_Clear_guard::~_Clear_guard(void)
0x180024196  add     rsp, 28h
0x18002419a  pop     r15
0x18002419c  pop     r14
0x18002419e  pop     r13
0x1800241a0  pop     r12
0x1800241a2  pop     rdi
0x1800241a3  pop     rsi
0x1800241a4  pop     rbp
0x1800241a5  pop     rbx
0x1800241a6  retn
```
