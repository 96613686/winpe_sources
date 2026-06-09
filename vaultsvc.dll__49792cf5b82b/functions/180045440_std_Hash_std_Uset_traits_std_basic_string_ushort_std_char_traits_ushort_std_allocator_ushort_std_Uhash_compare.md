# std::_Hash<std::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x180045440`
- end: `0x1800455e7`
- name: `?_Forced_rehash@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z`
- size: `423`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180030d14`

## callees

- `0x180038a28`
- `0x180041bac`
- `0x180042ed4`
- `0x180042f9c`
- `0x180045440`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180045480`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180045480`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Forced_rehash(
        _QWORD *a1,
        unsigned __int64 a2)
{
  unsigned __int64 v3; // rcx
  _QWORD *v4; // r12
  unsigned __int64 v5; // rcx
  __int64 *v6; // rsi
  __int64 v7; // rbx
  _QWORD *v8; // rbx
  _QWORD *v9; // rdi
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rbp
  __int64 v13; // r14
  _QWORD *v14; // rsi
  __int64 v15; // rcx
  _QWORD *v16; // r8
  _QWORD *v17; // rdx
  _QWORD *v18; // rcx
  _QWORD *v19; // rax
  _QWORD **v20; // r8
  _QWORD *v21; // r8
  _QWORD *v22; // rdx
  _QWORD *v23; // rcx
  _QWORD *v24; // rax
  _QWORD *v25; // rdx
  _QWORD *v26; // rax
  _QWORD *v27; // rcx
  __int64 v29; // [rsp+78h] [rbp+10h] BYREF

  LODWORD(v29) = 0;
  _BitScanReverse64(&v3, 0xFFFFFFFFFFFFFFFuLL);
  if ( a2 > 1LL << v3 )
    std::_Xlength_error("invalid hash bucket count");
  v4 = (_QWORD *)a1[1];
  LODWORD(v29) = 0;
  _BitScanReverse64(&v5, (a2 - 1) | 1);
  v6 = a1 + 3;
  v7 = 1LL << ((unsigned __int8)v5 + 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(
    a1 + 3,
    2 * v7,
    v4);
  a1[7] = v7;
  a1[6] = v7 - 1;
  v8 = *(_QWORD **)a1[1];
  v9 = v8;
  while ( v8 != v4 )
  {
    v9 = (_QWORD *)*v9;
    v10 = std::_Conditionally_enabled_hash<std::wstring,1>::operator()(v8 + 2);
    v12 = *v6;
    v13 = 2 * (a1[6] & v10);
    if ( *(_QWORD **)(*v6 + 16 * (a1[6] & v10)) == v4 )
    {
      *(_QWORD *)(v12 + 16 * (a1[6] & v10)) = v8;
      *(_QWORD *)(v12 + 8 * v13 + 8) = v8;
    }
    else
    {
      v14 = *(_QWORD **)(v12 + 16 * (a1[6] & v10) + 8);
      if ( (unsigned __int8)std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(
                              v11,
                              v8 + 2,
                              v14 + 2) )
      {
        while ( 1 )
        {
          v20 = (_QWORD **)(v14 + 1);
          if ( *(_QWORD **)(v12 + 8 * v13) == v14 )
            break;
          v14 = *v20;
          if ( !(unsigned __int8)std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(
                                   v15,
                                   v8 + 2,
                                   *v20 + 2) )
          {
            v21 = (_QWORD *)*v14;
            v22 = (_QWORD *)v8[1];
            *v22 = v9;
            v23 = (_QWORD *)v9[1];
            *v23 = v21;
            v24 = (_QWORD *)v21[1];
            *v24 = v8;
            v21[1] = v23;
            v9[1] = v22;
            v8[1] = v24;
            goto LABEL_15;
          }
        }
        v25 = (_QWORD *)v8[1];
        *v25 = v9;
        v26 = (_QWORD *)v9[1];
        *v26 = v14;
        v27 = *v20;
        *v27 = v8;
        *v20 = v26;
        v9[1] = v25;
        v8[1] = v27;
        *(_QWORD *)(v12 + 8 * v13) = v8;
      }
      else
      {
        v16 = (_QWORD *)*v14;
        if ( (_QWORD *)*v14 != v8 )
        {
          v17 = (_QWORD *)v8[1];
          *v17 = v9;
          v18 = (_QWORD *)v9[1];
          *v18 = v16;
          v19 = (_QWORD *)v16[1];
          *v19 = v8;
          v16[1] = v18;
          v9[1] = v17;
          v8[1] = v19;
        }
        *(_QWORD *)(v12 + 8 * v13 + 8) = v8;
      }
LABEL_15:
      v6 = a1 + 3;
    }
    v8 = v9;
  }
  v29 = 0;
  return std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Clear_guard::~_Clear_guard(&v29);
}

```

## disassembly

```asm
0x180045440  push    rbx
0x180045442  push    rbp
0x180045443  push    rsi
0x180045444  push    rdi
0x180045445  push    r12
0x180045447  push    r13
0x180045449  push    r14
0x18004544b  push    r15
0x18004544d  sub     rsp, 28h
0x180045451  mov     rax, 0FFFFFFFFFFFFFFFh
0x18004545b  mov     dword ptr [rsp+68h+arg_8], 0
0x180045463  mov     r13, rcx
0x180045466  mov     ebx, 1
0x18004546b  bsr     rcx, rax
0x18004546f  mov     eax, ebx
0x180045471  shl     rax, cl
0x180045474  cmp     rdx, rax
0x180045477  jbe     short loc_180045487
0x180045479  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x180045480  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180045487  mov     r12, [r13+8]
0x18004548b  lea     rax, [rdx-1]
0x18004548f  or      rax, rbx
0x180045492  mov     dword ptr [rsp+68h+arg_8], 0
0x18004549a  bsr     rcx, rax
0x18004549e  lea     rsi, [r13+18h]
0x1800454a2  mov     r8, r12
0x1800454a5  inc     ecx
0x1800454a7  shl     rbx, cl
0x1800454aa  mov     rcx, rsi
0x1800454ad  lea     rdx, [rbx+rbx]
0x1800454b1  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>)
0x1800454b6  lea     rax, [rbx-1]
0x1800454ba  mov     [r13+38h], rbx
0x1800454be  mov     [r13+30h], rax
0x1800454c2  mov     rbx, [r13+8]
0x1800454c6  mov     rbx, [rbx]
0x1800454c9  mov     rdi, rbx
0x1800454cc  cmp     rbx, r12
0x1800454cf  jz      loc_1800455C3
0x1800454d5  mov     rdi, [rdi]
0x1800454d8  lea     r15, [rbx+10h]
0x1800454dc  mov     rcx, r15
0x1800454df  call    ??R?$_Conditionally_enabled_hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$00@std@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Conditionally_enabled_hash<std::wstring,1>::operator()(std::wstring const &)
0x1800454e4  mov     rbp, [rsi]
0x1800454e7  mov     r14, rax
0x1800454ea  and     r14, [r13+30h]
0x1800454ee  add     r14, r14
0x1800454f1  cmp     [rbp+r14*8+0], r12
0x1800454f6  jnz     short loc_180045507
0x1800454f8  mov     [rbp+r14*8+0], rbx
0x1800454fd  mov     [rbp+r14*8+8], rbx
0x180045502  jmp     loc_1800455BB
0x180045507  mov     rsi, [rbp+r14*8+8]
0x18004550c  mov     rdx, r15
0x18004550f  lea     r8, [rsi+10h]
0x180045513  call    ??$?RV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V01@@?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z; std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(std::wstring const &,std::wstring const &)
0x180045518  test    al, al
0x18004551a  jnz     short loc_18004554C
0x18004551c  mov     r8, [rsi]
0x18004551f  cmp     r8, rbx
0x180045522  jz      short loc_180045545
0x180045524  mov     rdx, [rbx+8]
0x180045528  mov     [rdx], rdi
0x18004552b  mov     rcx, [rdi+8]
0x18004552f  mov     [rcx], r8
0x180045532  mov     rax, [r8+8]
0x180045536  mov     [rax], rbx
0x180045539  mov     [r8+8], rcx
0x18004553d  mov     [rdi+8], rdx
0x180045541  mov     [rbx+8], rax
0x180045545  mov     [rbp+r14*8+8], rbx
0x18004554a  jmp     short loc_1800455B7
0x18004554c  mov     rax, rsi
0x18004554f  lea     r8, [rsi+8]
0x180045553  cmp     [rbp+r14*8+0], rax
0x180045558  jz      short loc_180045593
0x18004555a  mov     rsi, [r8]
0x18004555d  mov     rdx, r15
0x180045560  lea     r8, [rsi+10h]
0x180045564  call    ??$?RV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V01@@?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z; std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(std::wstring const &,std::wstring const &)
0x180045569  test    al, al
0x18004556b  jnz     short loc_18004554C
0x18004556d  mov     r8, [rsi]
0x180045570  mov     rdx, [rbx+8]
0x180045574  mov     [rdx], rdi
0x180045577  mov     rcx, [rdi+8]
0x18004557b  mov     [rcx], r8
0x18004557e  mov     rax, [r8+8]
0x180045582  mov     [rax], rbx
0x180045585  mov     [r8+8], rcx
0x180045589  mov     [rdi+8], rdx
0x18004558d  mov     [rbx+8], rax
0x180045591  jmp     short loc_1800455B7
0x180045593  mov     rdx, [rbx+8]
0x180045597  mov     [rdx], rdi
0x18004559a  mov     rax, [rdi+8]
0x18004559e  mov     [rax], rsi
0x1800455a1  mov     rcx, [r8]
0x1800455a4  mov     [rcx], rbx
0x1800455a7  mov     [r8], rax
0x1800455aa  mov     [rdi+8], rdx
0x1800455ae  mov     [rbx+8], rcx
0x1800455b2  mov     [rbp+r14*8+0], rbx
0x1800455b7  lea     rsi, [r13+18h]
0x1800455bb  mov     rbx, rdi
0x1800455be  jmp     loc_1800454CC
0x1800455c3  lea     rcx, [rsp+68h+arg_8]
0x1800455c8  mov     [rsp+68h+arg_8], 0
0x1800455d1  call    ??1_Clear_guard@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Clear_guard::~_Clear_guard(void)
0x1800455d6  add     rsp, 28h
0x1800455da  pop     r15
0x1800455dc  pop     r14
0x1800455de  pop     r13
0x1800455e0  pop     r12
0x1800455e2  pop     rdi
0x1800455e3  pop     rsi
0x1800455e4  pop     rbp
0x1800455e5  pop     rbx
0x1800455e6  retn
```
