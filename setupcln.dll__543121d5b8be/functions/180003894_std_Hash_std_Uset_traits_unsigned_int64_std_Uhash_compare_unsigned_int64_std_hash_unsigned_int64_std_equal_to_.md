# std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Insert<unsigned __int64 const &,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned __int64>>,std::_Iterator_base0>>(unsigned __int64 const &,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned __int64>>,std::_Iterator_base0>)

- ea: `0x180003894`
- end: `0x18000397d`
- name: `??$_Insert@AEB_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@_K@std@@@std@@U_Iterator_base0@2@@std@@@?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@_K@std@@@std@@@std@@_N@1@AEB_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@_K@std@@@std@@U_Iterator_base0@2@@1@@Z`
- size: `233`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180008900`

## callees

- `0x180003894`
- `0x180008308`
- `0x1800083ac`
- `0x18000854c`
- `0x180008640`
- `0x180008a54`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Insert<unsigned __int64 const &,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned __int64>>,std::_Iterator_base0>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 *a4)
{
  __int64 v7; // rax
  __int64 v8; // rdi
  __int64 v9; // r10
  _QWORD *v10; // r11
  __int64 result; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  _BYTE v14[40]; // [rsp+20h] [rbp-28h] BYREF

  v7 = std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Hashval(
         a1,
         a3);
  v8 = *(_QWORD *)std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_End(
                    a1,
                    v14,
                    v7);
  while ( v8 != *(_QWORD *)(*(_QWORD *)(a1 + 16) + 16 * v9) )
  {
    v8 = *(_QWORD *)(v8 + 8);
    if ( *v10 == *(_QWORD *)(v8 + 16) )
    {
      std::list<unsigned __int64>::erase(a1, v14, a4);
      *(_QWORD *)a2 = v8;
      *(_BYTE *)(a2 + 8) = 0;
      return a2;
    }
  }
  v12 = *a4;
  if ( v8 != *a4 )
  {
    *(_QWORD *)a4[1] = v12;
    **(_QWORD **)(v12 + 8) = v8;
    **(_QWORD **)(v8 + 8) = a4;
    v13 = *(_QWORD *)(v8 + 8);
    *(_QWORD *)(v8 + 8) = *(_QWORD *)(v12 + 8);
    *(_QWORD *)(v12 + 8) = a4[1];
    a4[1] = v13;
  }
  std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Insert_bucket(
    a1,
    a4,
    v8,
    v9);
  try
  {
    std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Check_size(a1);
    *(_QWORD *)a2 = a4;
    *(_BYTE *)(a2 + 8) = 1;
    result = a2;
  }
  catch ( ... )
  {
    std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::erase(
      a1,
      v14,
      a4);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x180003894  mov     [rsp+arg_8], rbx
0x180003899  mov     [rsp+arg_18], r9
0x18000389e  mov     [rsp+arg_0], rcx
0x1800038a3  push    rsi
0x1800038a4  push    rdi
0x1800038a5  push    r14
0x1800038a7  sub     rsp, 30h
0x1800038ab  mov     rbx, r9
0x1800038ae  mov     r11, r8
0x1800038b1  mov     rsi, rdx
0x1800038b4  mov     r14, rcx
0x1800038b7  mov     rdx, r8
0x1800038ba  call    ?_Hashval@?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@IEBA_KAEB_K@Z; std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Hashval(unsigned __int64 const &)
0x1800038bf  mov     r10, rax
0x1800038c2  mov     r8, rax
0x1800038c5  lea     rdx, [rsp+48h+var_28]
0x1800038ca  mov     rcx, r14
0x1800038cd  call    ?_End@?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@IEAA?AV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@_K@std@@@std@@U_Iterator_base0@2@@2@_K@Z; std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_End(unsigned __int64)
0x1800038d2  mov     rdi, [rax]
0x1800038d5  mov     rcx, r10
0x1800038d8  add     rcx, rcx
0x1800038db  mov     rax, [r14+10h]
0x1800038df  mov     rdx, [rax+rcx*8]
0x1800038e3  cmp     rdi, rdx
0x1800038e6  jz      short loc_180003914
0x1800038e8  mov     rax, [rdi+8]
0x1800038ec  mov     rdi, rax
0x1800038ef  mov     rax, [rax+10h]
0x1800038f3  cmp     [r11], rax
0x1800038f6  jnz     short loc_1800038E3
0x1800038f8  mov     r8, rbx
0x1800038fb  lea     rdx, [rsp+48h+var_28]
0x180003900  mov     rcx, r14
0x180003903  call    ?erase@?$list@_KV?$allocator@_K@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@_K@std@@@std@@@2@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@_K@std@@@std@@@2@@Z; std::list<unsigned __int64>::erase(std::_List_const_iterator<std::_List_val<std::_List_simple_types<unsigned __int64>>>)
0x180003908  mov     [rsi], rdi
0x18000390b  mov     byte ptr [rsi+8], 0
0x18000390f  mov     rax, rsi
0x180003912  jmp     short loc_18000396E
0x180003914  mov     rdx, [rbx]
0x180003917  cmp     rdi, rdx
0x18000391a  jz      short loc_180003949
0x18000391c  mov     rax, [rbx+8]
0x180003920  mov     [rax], rdx
0x180003923  mov     rax, [rdx+8]
0x180003927  mov     [rax], rdi
0x18000392a  mov     rax, [rdi+8]
0x18000392e  mov     [rax], rbx
0x180003931  mov     rcx, [rdi+8]
0x180003935  mov     rax, [rdx+8]
0x180003939  mov     [rdi+8], rax
0x18000393d  mov     rax, [rbx+8]
0x180003941  mov     [rdx+8], rax
0x180003945  mov     [rbx+8], rcx
0x180003949  mov     r9, r10
0x18000394c  mov     r8, rdi
0x18000394f  mov     rdx, rbx
0x180003952  mov     rcx, r14
0x180003955  call    ?_Insert_bucket@?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@IEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@_K@std@@@std@@U_Iterator_base0@2@@2@0_K@Z; std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Insert_bucket(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned __int64>>,std::_Iterator_base0>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned __int64>>,std::_Iterator_base0>,unsigned __int64)
0x18000395a  nop
0x18000395b  mov     rcx, r14
0x18000395e  call    ?_Check_size@?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@IEAAXXZ; std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Check_size(void)
0x180003963  nop
0x180003964  mov     [rsi], rbx
0x180003967  mov     byte ptr [rsi+8], 1
0x18000396b  mov     rax, rsi
0x18000396e  mov     rbx, [rsp+48h+arg_8]
0x180003973  add     rsp, 30h
0x180003977  pop     r14
0x180003979  pop     rdi
0x18000397a  pop     rsi
0x18000397b  retn
```
