# std::_Hash<std::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::emplace<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &&)

- ea: `0x180030d14`
- end: `0x180030e96`
- name: `??$emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z`
- size: `386`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18001dbe0`

## callees

- `0x180030d14`
- `0x180030e9c`
- `0x180032da8`
- `0x180037e58`
- `0x180041bac`
- `0x180042ab8`
- `0x180042f9c`
- `0x1800450bc`
- `0x180045440`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180030e54`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180030e54`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r12
  __int64 v9; // rcx
  __int64 v10; // rbx
  __int64 v11; // rbp
  __int64 v12; // rbp
  __int64 v13; // rbx
  __int64 v14; // rcx
  __int64 v15; // rdx
  float v16; // xmm0_4
  __int64 v17; // rcx
  float v18; // xmm1_4
  __int64 v20; // rax
  __int64 v21; // rax
  _QWORD v22[9]; // [rsp+20h] [rbp-48h] BYREF

  v8 = std::_Conditionally_enabled_hash<std::wstring,1>::operator()(a3);
  v9 = *(_QWORD *)(a1 + 24);
  v10 = *(_QWORD *)(v9 + 16 * (v8 & *(_QWORD *)(a1 + 48)) + 8);
  v11 = *(_QWORD *)(a1 + 8);
  if ( v10 == v11 )
  {
LABEL_6:
    if ( *(_QWORD *)(a1 + 16) == 0x555555555555555LL )
      std::_Xlength_error("unordered_map/set too long");
    v22[0] = a1 + 8;
    v13 = std::_Allocate<16,std::_Default_allocate_traits>(48, v6, v7);
    v22[1] = v13;
    std::_Default_allocator_traits<std::allocator<std::_List_node<std::wstring,void *>>>::construct<std::wstring,std::wstring>(
      v14,
      v13 + 16,
      a3);
    v15 = *(_QWORD *)(a1 + 16) + 1LL;
    if ( v15 < 0 )
      v16 = (float)(v15 & 1 | (unsigned int)((unsigned __int64)v15 >> 1))
          + (float)(v15 & 1 | (unsigned int)((unsigned __int64)v15 >> 1));
    else
      v16 = (float)(int)v15;
    v17 = *(_QWORD *)(a1 + 56);
    if ( v17 < 0 )
    {
      v20 = *(_QWORD *)(a1 + 56) & 1LL | ((unsigned __int64)v17 >> 1);
      v18 = (float)(int)v20 + (float)(int)v20;
    }
    else
    {
      v18 = (float)(int)v17;
    }
    if ( (float)(v16 / v18) > *(float *)a1 )
    {
      v21 = std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Desired_grow_bucket_count(a1);
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Forced_rehash(
        a1,
        v21);
      v11 = *(_QWORD *)((__int64 (__fastcall *)(__int64, _QWORD *, __int64, __int64))std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>)(
                         a1,
                         v22,
                         v13 + 16,
                         v8);
    }
    *(_QWORD *)a2 = std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Insert_new_node_before(
                      a1,
                      v8,
                      v11,
                      v13,
                      v22[0]);
    *(_BYTE *)(a2 + 8) = 1;
  }
  else
  {
    v12 = *(_QWORD *)(v9 + 16 * (v8 & *(_QWORD *)(a1 + 48)));
    while ( (unsigned __int8)std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(
                               v9,
                               a3,
                               v10 + 16) )
    {
      if ( v10 == v12 )
      {
        v11 = v10;
        goto LABEL_6;
      }
      v10 = *(_QWORD *)(v10 + 8);
    }
    *(_QWORD *)a2 = v10;
    *(_BYTE *)(a2 + 8) = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x180030d14  push    rbx
0x180030d16  push    rbp
0x180030d17  push    rsi
0x180030d18  push    rdi
0x180030d19  push    r12
0x180030d1b  push    r14
0x180030d1d  push    r15
0x180030d1f  sub     rsp, 30h
0x180030d23  mov     r14, r8
0x180030d26  mov     rsi, rdx
0x180030d29  mov     rdi, rcx
0x180030d2c  mov     rcx, r8
0x180030d2f  call    ??R?$_Conditionally_enabled_hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$00@std@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Conditionally_enabled_hash<std::wstring,1>::operator()(std::wstring const &)
0x180030d34  mov     r12, rax
0x180030d37  mov     rax, [rdi+30h]
0x180030d3b  and     rax, r12
0x180030d3e  add     rax, rax
0x180030d41  mov     rcx, [rdi+18h]
0x180030d45  mov     rbx, [rcx+rax*8+8]
0x180030d4a  lea     r15, [rdi+8]
0x180030d4e  mov     rbp, [r15]
0x180030d51  cmp     rbx, rbp
0x180030d54  jz      short loc_180030D7D
0x180030d56  mov     rbp, [rcx+rax*8]
0x180030d5a  lea     r8, [rbx+10h]
0x180030d5e  mov     rdx, r14
0x180030d61  call    ??$?RV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V01@@?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z; std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(std::wstring const &,std::wstring const &)
0x180030d66  test    al, al
0x180030d68  jz      loc_180030E8A
0x180030d6e  cmp     rbx, rbp
0x180030d71  jz      loc_180030E45
0x180030d77  mov     rbx, [rbx+8]
0x180030d7b  jmp     short loc_180030D5A
0x180030d7d  mov     rax, 555555555555555h
0x180030d87  cmp     [rdi+10h], rax
0x180030d8b  jz      loc_180030E4D
0x180030d91  mov     [rsp+68h+var_48], r15
0x180030d96  mov     [rsp+68h+var_40], 0
0x180030d9f  mov     ecx, 30h ; '0'
0x180030da4  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180030da9  mov     rbx, rax
0x180030dac  mov     [rsp+68h+var_40], rax
0x180030db1  lea     rdx, [rax+10h]
0x180030db5  mov     r8, r14
0x180030db8  call    ??$construct@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@?$_Default_allocator_traits@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV31@@Z; std::_Default_allocator_traits<std::allocator<std::_List_node<std::wstring,void *>>>::construct<std::wstring,std::wstring>(std::allocator<std::_List_node<std::wstring,void *>> &,std::wstring * const,std::wstring &&)
0x180030dbd  nop
0x180030dbe  mov     rdx, [rdi+10h]
0x180030dc2  add     rdx, 1
0x180030dc6  xorps   xmm0, xmm0
0x180030dc9  js      short loc_180030E14
0x180030dcb  cvtsi2ss xmm0, rdx
0x180030dd0  mov     rcx, [rdi+38h]
0x180030dd4  xorps   xmm1, xmm1
0x180030dd7  test    rcx, rcx
0x180030dda  js      short loc_180030E2E
0x180030ddc  cvtsi2ss xmm1, rcx
0x180030de1  divss   xmm0, xmm1
0x180030de5  comiss  xmm0, dword ptr [rdi]
0x180030de8  ja      short loc_180030E5B
0x180030dea  mov     r9, rbx
0x180030ded  mov     r8, rbp
0x180030df0  mov     rdx, r12
0x180030df3  mov     rcx, rdi
0x180030df6  call    ?_Insert_new_node_before@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAAPEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@2@_KQEAU32@1@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Insert_new_node_before(unsigned __int64,std::_List_node<std::wstring,void *> * const,std::_List_node<std::wstring,void *> * const)
0x180030dfb  mov     [rsi], rax
0x180030dfe  mov     byte ptr [rsi+8], 1
0x180030e02  mov     rax, rsi
0x180030e05  add     rsp, 30h
0x180030e09  pop     r15
0x180030e0b  pop     r14
0x180030e0d  pop     r12
0x180030e0f  pop     rdi
0x180030e10  pop     rsi
0x180030e11  pop     rbp
0x180030e12  pop     rbx
0x180030e13  retn
0x180030e14  mov     rcx, rdx
0x180030e17  shr     rcx, 1
0x180030e1a  mov     rax, rdx
0x180030e1d  and     eax, 1
0x180030e20  or      rcx, rax
0x180030e23  cvtsi2ss xmm0, rcx
0x180030e28  addss   xmm0, xmm0
0x180030e2c  jmp     short loc_180030DD0
0x180030e2e  mov     rax, rcx
0x180030e31  shr     rax, 1
0x180030e34  and     ecx, 1
0x180030e37  or      rax, rcx
0x180030e3a  cvtsi2ss xmm1, rax
0x180030e3f  addss   xmm1, xmm1
0x180030e43  jmp     short loc_180030DE1
0x180030e45  mov     rbp, rbx
0x180030e48  jmp     loc_180030D7D
0x180030e4d  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x180030e54  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180030e5b  mov     rcx, rdi
0x180030e5e  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x180030e63  mov     rdx, rax
0x180030e66  mov     rcx, rdi
0x180030e69  call    ?_Forced_rehash@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Forced_rehash(unsigned __int64)
0x180030e6e  lea     r8, [rbx+10h]
0x180030e72  mov     r9, r12
0x180030e75  lea     rdx, [rsp+68h+var_48]
0x180030e7a  mov     rcx, rdi
0x180030e7d  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x180030e82  mov     rbp, [rax]
0x180030e85  jmp     loc_180030DEA
0x180030e8a  mov     [rsi], rbx
0x180030e8d  mov     byte ptr [rsi+8], 0
0x180030e91  jmp     loc_180030E02
```
