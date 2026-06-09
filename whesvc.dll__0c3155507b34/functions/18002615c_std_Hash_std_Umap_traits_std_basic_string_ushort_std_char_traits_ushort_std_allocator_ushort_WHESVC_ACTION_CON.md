# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,_WHESVC_ACTION_CONFIG_VALUE,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,_WHESVC_ACTION_CONFIG_VALUE>>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x18002615c`
- end: `0x180026385`
- name: `?_Forced_rehash@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_WHESVC_ACTION_CONFIG_VALUE@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_WHESVC_ACTION_CONFIG_VALUE@@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z`
- size: `553`
- prototype: `void __fastcall(_QWORD *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025dcc`

## callees

- `0x180016b28`
- `0x18001997c`
- `0x180026088`
- `0x18002615c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002619a`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002619a`

## pseudocode

```c
void __fastcall std::_Hash<std::_Umap_traits<std::wstring,_WHESVC_ACTION_CONFIG_VALUE,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,_WHESVC_ACTION_CONFIG_VALUE>>,0>>::_Forced_rehash(
        _QWORD *a1,
        unsigned __int64 a2)
{
  unsigned __int64 v3; // rcx
  unsigned __int64 v4; // rbp
  unsigned __int64 v5; // rcx
  __int64 *v6; // rsi
  __int64 v7; // rbx
  _QWORD *v8; // rbx
  _QWORD *v9; // rdi
  const wchar_t **v10; // r15
  const wchar_t *v11; // rdx
  __int64 v12; // r9
  unsigned __int64 v13; // rcx
  __int64 i; // r14
  __int64 v15; // rax
  __int64 v16; // r12
  __int64 v17; // r14
  _QWORD *v18; // rsi
  const wchar_t *v19; // rdx
  const wchar_t *v20; // rcx
  _QWORD *v21; // r8
  _QWORD *v22; // rdx
  _QWORD *v23; // rcx
  _QWORD *v24; // rax
  _QWORD *v25; // r8
  const wchar_t *v26; // rdx
  size_t v27; // r8
  const wchar_t *v28; // rcx
  _QWORD *v29; // r8
  _QWORD *v30; // rdx
  _QWORD *v31; // rcx
  _QWORD *v32; // rax
  _QWORD *v33; // rdx
  _QWORD *v34; // rax
  _QWORD *v35; // rcx
  unsigned __int64 *v36; // [rsp+78h] [rbp+10h] BYREF

  LODWORD(v36) = 0;
  _BitScanReverse64(&v3, 0xFFFFFFFFFFFFFFFuLL);
  if ( a2 > 1LL << v3 )
    std::_Xlength_error("invalid hash bucket count");
  v4 = a1[1];
  LODWORD(v36) = 0;
  _BitScanReverse64(&v5, (a2 - 1) | 1);
  v6 = a1 + 3;
  v7 = 1LL << ((unsigned __int8)v5 + 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,bool (*)(void)>>>>>>::_Assign_grow(
    (__int64)(a1 + 3),
    2 * v7,
    v4);
  a1[7] = v7;
  a1[6] = v7 - 1;
  v8 = *(_QWORD **)a1[1];
  v9 = v8;
  while ( v8 != (_QWORD *)v4 )
  {
    v9 = (_QWORD *)*v9;
    v10 = (const wchar_t **)(v8 + 2);
    v11 = (const wchar_t *)(v8 + 2);
    v12 = v8[4];
    if ( v8[5] > 7u )
      v11 = *v10;
    v13 = 0;
    for ( i = 0xCBF29CE484222325uLL; v13 < 2 * v12; i = 0x100000001B3LL * (v15 ^ i) )
      v15 = *((unsigned __int8 *)v11 + v13++);
    v16 = *v6;
    v17 = 2 * (a1[6] & i);
    if ( *(_QWORD *)(*v6 + 8 * v17) == v4 )
    {
      *(_QWORD *)(v16 + 8 * v17) = v8;
      *(_QWORD *)(v16 + 8 * v17 + 8) = v8;
    }
    else
    {
      v18 = *(_QWORD **)(v16 + 8 * v17 + 8);
      v19 = (const wchar_t *)(v18 + 2);
      if ( v18[5] > 7u )
        v19 = *(const wchar_t **)v19;
      v20 = (const wchar_t *)(v8 + 2);
      if ( v8[5] > 7u )
        v20 = *v10;
      if ( v12 == v18[4] && (!v12 || !wmemcmp(v20, v19, v8[4])) )
      {
        v21 = (_QWORD *)*v18;
        if ( (_QWORD *)*v18 != v8 )
        {
          v22 = (_QWORD *)v8[1];
          *v22 = v9;
          v23 = (_QWORD *)v9[1];
          *v23 = v21;
          v24 = (_QWORD *)v21[1];
          *v24 = v8;
          v21[1] = v23;
          v9[1] = v22;
          v8[1] = v24;
        }
        *(_QWORD *)(v16 + 8 * v17 + 8) = v8;
      }
      else
      {
        while ( 1 )
        {
          v25 = v18 + 1;
          if ( *(_QWORD **)(v16 + 8 * v17) == v18 )
            break;
          v18 = (_QWORD *)*v25;
          v26 = (const wchar_t *)(*v25 + 16LL);
          if ( *(_QWORD *)(*v25 + 40LL) > 7u )
            v26 = *(const wchar_t **)v26;
          v27 = v8[4];
          if ( v8[5] <= 7u )
            v28 = (const wchar_t *)(v8 + 2);
          else
            v28 = *v10;
          if ( v27 == v18[4] && (!v27 || !wmemcmp(v28, v26, v27)) )
          {
            v29 = (_QWORD *)*v18;
            v30 = (_QWORD *)v8[1];
            *v30 = v9;
            v31 = (_QWORD *)v9[1];
            *v31 = v29;
            v32 = (_QWORD *)v29[1];
            *v32 = v8;
            v29[1] = v31;
            v9[1] = v30;
            v8[1] = v32;
            goto LABEL_32;
          }
        }
        v33 = (_QWORD *)v8[1];
        *v33 = v9;
        v34 = (_QWORD *)v9[1];
        *v34 = v18;
        v35 = (_QWORD *)*v25;
        *v35 = v8;
        *v25 = v34;
        v9[1] = v33;
        v8[1] = v35;
        *(_QWORD *)(v16 + 8 * v17) = v8;
      }
LABEL_32:
      v6 = a1 + 3;
    }
    v8 = v9;
  }
  v36 = 0;
  std::_Hash<std::_Umap_traits<std::wstring,_WHESVC_ACTION_CONFIG_VALUE,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,_WHESVC_ACTION_CONFIG_VALUE>>,0>>::_Clear_guard::~_Clear_guard(&v36);
}

```

## disassembly

```asm
0x18002615c  push    rbx
0x18002615e  push    rbp
0x18002615f  push    rsi
0x180026160  push    rdi
0x180026161  push    r12
0x180026163  push    r13
0x180026165  push    r14
0x180026167  push    r15
0x180026169  sub     rsp, 28h
0x18002616d  mov     rax, 0FFFFFFFFFFFFFFFh
0x180026177  mov     dword ptr [rsp+68h+arg_8], 0
0x18002617f  mov     r13, rcx
0x180026182  bsr     rcx, rax
0x180026186  mov     eax, 1
0x18002618b  shl     rax, cl
0x18002618e  cmp     rdx, rax
0x180026191  jbe     short loc_1800261A1
0x180026193  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x18002619a  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800261a1  mov     rbp, [r13+8]
0x1800261a5  lea     rax, [rdx-1]
0x1800261a9  or      rax, 1
0x1800261ad  mov     dword ptr [rsp+68h+arg_8], 0
0x1800261b5  bsr     rcx, rax
0x1800261b9  mov     ebx, 1
0x1800261be  lea     rsi, [r13+18h]
0x1800261c2  inc     ecx
0x1800261c4  mov     r8, rbp
0x1800261c7  shl     rbx, cl
0x1800261ca  mov     rcx, rsi
0x1800261cd  lea     rdx, [rbx+rbx]
0x1800261d1  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@P6A_NXZ@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@P6A_NXZ@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,bool (*)(void)>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::string const,bool (*)(void)>>>>)
0x1800261d6  lea     rax, [rbx-1]
0x1800261da  mov     [r13+38h], rbx
0x1800261de  mov     [r13+30h], rax
0x1800261e2  mov     rbx, [r13+8]
0x1800261e6  mov     rbx, [rbx]
0x1800261e9  mov     rdi, rbx
0x1800261ec  cmp     rbx, rbp
0x1800261ef  jz      loc_180026361
0x1800261f5  mov     rdi, [rdi]
0x1800261f8  lea     r15, [rbx+10h]
0x1800261fc  cmp     qword ptr [r15+18h], 7
0x180026201  mov     rdx, r15
0x180026204  mov     r9, [r15+10h]
0x180026208  jbe     short loc_18002620D
0x18002620a  mov     rdx, [r15]
0x18002620d  lea     r8, [r9+r9]
0x180026211  xor     ecx, ecx
0x180026213  mov     r14, 0CBF29CE484222325h
0x18002621d  test    r8, r8
0x180026220  jz      short loc_18002623F
0x180026222  movzx   eax, byte ptr [rdx+rcx]
0x180026226  mov     r10, 100000001B3h
0x180026230  xor     r14, rax
0x180026233  inc     rcx
0x180026236  imul    r14, r10
0x18002623a  cmp     rcx, r8
0x18002623d  jb      short loc_180026222
0x18002623f  and     r14, [r13+30h]
0x180026243  mov     r12, [rsi]
0x180026246  add     r14, r14
0x180026249  cmp     [r12+r14*8], rbp
0x18002624d  jnz     short loc_18002625D
0x18002624f  mov     [r12+r14*8], rbx
0x180026253  mov     [r12+r14*8+8], rbx
0x180026258  jmp     loc_180026359
0x18002625d  mov     rsi, [r12+r14*8+8]
0x180026262  lea     rdx, [rsi+10h]
0x180026266  cmp     qword ptr [rdx+18h], 7
0x18002626b  mov     rax, [rdx+10h]
0x18002626f  jbe     short loc_180026274
0x180026271  mov     rdx, [rdx]; S2
0x180026274  cmp     qword ptr [r15+18h], 7
0x180026279  mov     rcx, r15
0x18002627c  jbe     short loc_180026281
0x18002627e  mov     rcx, [r15]; S1
0x180026281  cmp     r9, rax
0x180026284  jnz     short loc_1800262CA
0x180026286  test    r9, r9
0x180026289  jz      short loc_180026297
0x18002628b  mov     r8, r9; N
0x18002628e  call    wmemcmp
0x180026293  test    eax, eax
0x180026295  jnz     short loc_1800262CA
0x180026297  mov     r8, [rsi]
0x18002629a  cmp     r8, rbx
0x18002629d  jz      short loc_1800262C0
0x18002629f  mov     rdx, [rbx+8]
0x1800262a3  mov     [rdx], rdi
0x1800262a6  mov     rcx, [rdi+8]
0x1800262aa  mov     [rcx], r8
0x1800262ad  mov     rax, [r8+8]
0x1800262b1  mov     [rax], rbx
0x1800262b4  mov     [r8+8], rcx
0x1800262b8  mov     [rdi+8], rdx
0x1800262bc  mov     [rbx+8], rax
0x1800262c0  mov     [r12+r14*8+8], rbx
0x1800262c5  jmp     loc_180026355
0x1800262ca  lea     r8, [rsi+8]
0x1800262ce  cmp     [r12+r14*8], rsi
0x1800262d2  jz      short loc_180026332
0x1800262d4  mov     rsi, [r8]
0x1800262d7  cmp     qword ptr [rsi+28h], 7
0x1800262dc  lea     rdx, [rsi+10h]
0x1800262e0  jbe     short loc_1800262E5
0x1800262e2  mov     rdx, [rdx]; S2
0x1800262e5  cmp     qword ptr [r15+18h], 7
0x1800262ea  mov     r8, [r15+10h]; N
0x1800262ee  jbe     short loc_1800262F5
0x1800262f0  mov     rcx, [r15]
0x1800262f3  jmp     short loc_1800262F8
0x1800262f5  mov     rcx, r15; S1
0x1800262f8  cmp     r8, [rsi+20h]
0x1800262fc  jnz     short loc_1800262CA
0x1800262fe  test    r8, r8
0x180026301  jz      short loc_18002630C
0x180026303  call    wmemcmp
0x180026308  test    eax, eax
0x18002630a  jnz     short loc_1800262CA
0x18002630c  mov     r8, [rsi]
0x18002630f  mov     rdx, [rbx+8]
0x180026313  mov     [rdx], rdi
0x180026316  mov     rcx, [rdi+8]
0x18002631a  mov     [rcx], r8
0x18002631d  mov     rax, [r8+8]
0x180026321  mov     [rax], rbx
0x180026324  mov     [r8+8], rcx
0x180026328  mov     [rdi+8], rdx
0x18002632c  mov     [rbx+8], rax
0x180026330  jmp     short loc_180026355
0x180026332  mov     rdx, [rbx+8]
0x180026336  mov     [rdx], rdi
0x180026339  mov     rax, [rdi+8]
0x18002633d  mov     [rax], rsi
0x180026340  mov     rcx, [r8]
0x180026343  mov     [rcx], rbx
0x180026346  mov     [r8], rax
0x180026349  mov     [rdi+8], rdx
0x18002634d  mov     [rbx+8], rcx
0x180026351  mov     [r12+r14*8], rbx
0x180026355  lea     rsi, [r13+18h]
0x180026359  mov     rbx, rdi
0x18002635c  jmp     loc_1800261EC
0x180026361  lea     rcx, [rsp+68h+arg_8]
0x180026366  mov     [rsp+68h+arg_8], 0
0x18002636f  call    ??1_Clear_guard@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_WHESVC_ACTION_CONFIG_VALUE@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_WHESVC_ACTION_CONFIG_VALUE@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,_WHESVC_ACTION_CONFIG_VALUE,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,_WHESVC_ACTION_CONFIG_VALUE>>,0>>::_Clear_guard::~_Clear_guard(void)
0x180026374  add     rsp, 28h
0x180026378  pop     r15
0x18002637a  pop     r14
0x18002637c  pop     r13
0x18002637e  pop     r12
0x180026380  pop     rdi
0x180026381  pop     rsi
0x180026382  pop     rbp
0x180026383  pop     rbx
0x180026384  retn
```
