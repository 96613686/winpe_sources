# std::_Hash<std::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::_Forced_rehash(unsigned __int64)

- ea: `0x180034be8`
- end: `0x180034d94`
- name: `?_Forced_rehash@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z`
- size: `428`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180034df4`

## callees

- `0x1800311c0`
- `0x1800333c4`
- `0x180033634`
- `0x180034728`
- `0x180034be8`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180034c29`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180034c29`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Forced_rehash(
        _QWORD *a1,
        unsigned __int64 a2)
{
  unsigned __int64 v3; // rcx
  unsigned __int64 v4; // rcx
  __int64 v5; // rbx
  _QWORD *v6; // rbp
  __int64 *v7; // rsi
  _QWORD *v8; // rbx
  _QWORD *v9; // rdi
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // r14
  __int64 v13; // r15
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
  _QWORD *v29; // [rsp+20h] [rbp-58h] BYREF

  _BitScanReverse64(&v3, 0xFFFFFFFFFFFFFFFuLL);
  if ( a2 > 1LL << v3 )
    std::_Xlength_error("invalid hash bucket count");
  _BitScanReverse64(&v4, (a2 - 1) | 1);
  v5 = 1LL << ((unsigned __int8)v4 + 1);
  v6 = (_QWORD *)a1[1];
  v7 = a1 + 3;
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(
    a1 + 3,
    2 * v5,
    v6);
  a1[6] = v5 - 1;
  a1[7] = v5;
  v29 = a1;
  v8 = *(_QWORD **)a1[1];
  v9 = v8;
  while ( v8 != v6 )
  {
    v9 = (_QWORD *)*v9;
    v10 = std::_Conditionally_enabled_hash<std::wstring,1>::operator()(v8 + 2);
    v12 = 2 * (a1[6] & v10);
    v13 = *v7;
    if ( *(_QWORD **)(*v7 + 16 * (a1[6] & v10)) == v6 )
    {
      *(_QWORD *)(v13 + 16 * (a1[6] & v10)) = v8;
      *(_QWORD *)(v13 + 8 * v12 + 8) = v8;
    }
    else
    {
      v14 = *(_QWORD **)(v13 + 16 * (a1[6] & v10) + 8);
      if ( (unsigned __int8)std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(
                              v11,
                              v8 + 2,
                              v14 + 2) )
      {
        while ( 1 )
        {
          v20 = (_QWORD **)(v14 + 1);
          if ( *(_QWORD **)(v13 + 8 * v12) == v14 )
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
        *(_QWORD *)(v13 + 8 * v12) = v8;
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
        *(_QWORD *)(v13 + 8 * v12 + 8) = v8;
      }
LABEL_15:
      v7 = a1 + 3;
    }
    v8 = v9;
  }
  v29 = 0;
  return std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Clear_guard::~_Clear_guard(&v29);
}

```

## disassembly

```asm
0x180034be8  mov     rax, rsp
0x180034beb  push    rbx
0x180034bec  push    rbp
0x180034bed  push    rsi
0x180034bee  push    rdi
0x180034bef  push    r12
0x180034bf1  push    r13
0x180034bf3  push    r14
0x180034bf5  push    r15
0x180034bf7  sub     rsp, 38h
0x180034bfb  mov     r13, rcx
0x180034bfe  mov     dword ptr [rax+10h], 0
0x180034c05  mov     rax, 0FFFFFFFFFFFFFFFh
0x180034c0f  bsr     rcx, rax
0x180034c13  mov     ebx, 1
0x180034c18  mov     eax, ebx
0x180034c1a  shl     rax, cl
0x180034c1d  cmp     rdx, rax
0x180034c20  jbe     short loc_180034C30
0x180034c22  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x180034c29  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180034c30  mov     [rsp+78h+arg_8], 0
0x180034c3b  lea     rax, [rdx-1]
0x180034c3f  or      rax, rbx
0x180034c42  bsr     rcx, rax
0x180034c46  inc     ecx
0x180034c48  shl     rbx, cl
0x180034c4b  mov     rbp, [r13+8]
0x180034c4f  lea     rsi, [r13+18h]
0x180034c53  lea     rdx, [rbx+rbx]
0x180034c57  mov     r8, rbp
0x180034c5a  mov     rcx, rsi
0x180034c5d  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>)
0x180034c62  lea     rax, [rbx-1]
0x180034c66  mov     [r13+30h], rax
0x180034c6a  mov     [r13+38h], rbx
0x180034c6e  mov     [rsp+78h+var_58], r13
0x180034c73  mov     rbx, [r13+8]
0x180034c77  mov     rbx, [rbx]
0x180034c7a  mov     rdi, rbx
0x180034c7d  cmp     rbx, rbp
0x180034c80  jz      loc_180034D70
0x180034c86  mov     rdi, [rdi]
0x180034c89  lea     r12, [rbx+10h]
0x180034c8d  mov     rcx, r12
0x180034c90  call    ??R?$_Conditionally_enabled_hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$00@std@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Conditionally_enabled_hash<std::wstring,1>::operator()(std::wstring const &)
0x180034c95  mov     r14, rax
0x180034c98  and     r14, [r13+30h]
0x180034c9c  add     r14, r14
0x180034c9f  mov     r15, [rsi]
0x180034ca2  cmp     [r15+r14*8], rbp
0x180034ca6  jnz     short loc_180034CB6
0x180034ca8  mov     [r15+r14*8], rbx
0x180034cac  mov     [r15+r14*8+8], rbx
0x180034cb1  jmp     loc_180034D68
0x180034cb6  mov     rsi, [r15+r14*8+8]
0x180034cbb  lea     r8, [rsi+10h]
0x180034cbf  mov     rdx, r12
0x180034cc2  call    ??$?RV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V01@@?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z; std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(std::wstring const &,std::wstring const &)
0x180034cc7  test    al, al
0x180034cc9  jnz     short loc_180034CFB
0x180034ccb  mov     r8, [rsi]
0x180034cce  cmp     r8, rbx
0x180034cd1  jz      short loc_180034CF4
0x180034cd3  mov     rdx, [rbx+8]
0x180034cd7  mov     [rdx], rdi
0x180034cda  mov     rcx, [rdi+8]
0x180034cde  mov     [rcx], r8
0x180034ce1  mov     rax, [r8+8]
0x180034ce5  mov     [rax], rbx
0x180034ce8  mov     [r8+8], rcx
0x180034cec  mov     [rdi+8], rdx
0x180034cf0  mov     [rbx+8], rax
0x180034cf4  mov     [r15+r14*8+8], rbx
0x180034cf9  jmp     short loc_180034D64
0x180034cfb  mov     rax, rsi
0x180034cfe  lea     r8, [rsi+8]
0x180034d02  cmp     [r15+r14*8], rax
0x180034d06  jz      short loc_180034D41
0x180034d08  mov     rsi, [r8]
0x180034d0b  lea     r8, [rsi+10h]
0x180034d0f  mov     rdx, r12
0x180034d12  call    ??$?RV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V01@@?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z; std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(std::wstring const &,std::wstring const &)
0x180034d17  test    al, al
0x180034d19  jnz     short loc_180034CFB
0x180034d1b  mov     r8, [rsi]
0x180034d1e  mov     rdx, [rbx+8]
0x180034d22  mov     [rdx], rdi
0x180034d25  mov     rcx, [rdi+8]
0x180034d29  mov     [rcx], r8
0x180034d2c  mov     rax, [r8+8]
0x180034d30  mov     [rax], rbx
0x180034d33  mov     [r8+8], rcx
0x180034d37  mov     [rdi+8], rdx
0x180034d3b  mov     [rbx+8], rax
0x180034d3f  jmp     short loc_180034D64
0x180034d41  mov     rdx, [rbx+8]
0x180034d45  mov     [rdx], rdi
0x180034d48  mov     rax, [rdi+8]
0x180034d4c  mov     [rax], rsi
0x180034d4f  mov     rcx, [r8]
0x180034d52  mov     [rcx], rbx
0x180034d55  mov     [r8], rax
0x180034d58  mov     [rdi+8], rdx
0x180034d5c  mov     [rbx+8], rcx
0x180034d60  mov     [r15+r14*8], rbx
0x180034d64  lea     rsi, [r13+18h]
0x180034d68  mov     rbx, rdi
0x180034d6b  jmp     loc_180034C7D
0x180034d70  mov     [rsp+78h+var_58], 0
0x180034d79  lea     rcx, [rsp+78h+var_58]
0x180034d7e  call    ??1_Clear_guard@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Clear_guard::~_Clear_guard(void)
0x180034d83  add     rsp, 38h
0x180034d87  pop     r15
0x180034d89  pop     r14
0x180034d8b  pop     r13
0x180034d8d  pop     r12
0x180034d8f  pop     rdi
0x180034d90  pop     rsi
0x180034d91  pop     rbp
0x180034d92  pop     rbx
0x180034d93  retn
```
