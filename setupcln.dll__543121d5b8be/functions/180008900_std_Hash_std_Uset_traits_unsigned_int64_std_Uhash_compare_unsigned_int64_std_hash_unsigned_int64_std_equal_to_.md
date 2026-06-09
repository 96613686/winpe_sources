# std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Reinsert(void)

- ea: `0x180008900`
- end: `0x18000894d`
- name: `?_Reinsert@?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@IEAAXXZ`
- size: `77`
- prototype: `__int64 **__fastcall(__int64 ***)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008308`

## callees

- `0x180003894`
- `0x180008900`

## pseudocode

```c
__int64 **__fastcall std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Reinsert(
        __int64 ***a1)
{
  __int64 **result; // rax
  __int64 *v3; // rsi
  __int64 *v4; // rbx
  _BYTE v5[24]; // [rsp+20h] [rbp-18h] BYREF

  result = *a1;
  if ( *result != (__int64 *)result )
  {
    v3 = result[1];
    do
    {
      v4 = **a1;
      result = (__int64 **)std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Insert<unsigned __int64 const &,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned __int64>>,std::_Iterator_base0>>(
                             (__int64)a1,
                             (__int64)v5,
                             (__int64)(v4 + 2),
                             v4);
    }
    while ( v4 != v3 );
  }
  return result;
}

```

## disassembly

```asm
0x180008900  mov     [rsp+arg_0], rbx
0x180008905  mov     [rsp+arg_8], rsi
0x18000890a  push    rdi
0x18000890b  sub     rsp, 30h
0x18000890f  mov     rax, [rcx]
0x180008912  mov     rdi, rcx
0x180008915  cmp     [rax], rax
0x180008918  jz      short loc_18000893D
0x18000891a  mov     rsi, [rax+8]
0x18000891e  mov     rbx, [rdi]
0x180008921  lea     rdx, [rsp+38h+var_18]
0x180008926  mov     rcx, rdi
0x180008929  mov     rbx, [rbx]
0x18000892c  mov     r9, rbx
0x18000892f  lea     r8, [rbx+10h]
0x180008933  call    ??$_Insert@AEB_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@_K@std@@@std@@U_Iterator_base0@2@@std@@@?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@_K@std@@@std@@@std@@_N@1@AEB_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@_K@std@@@std@@U_Iterator_base0@2@@1@@Z; std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::_Insert<unsigned __int64 const &,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned __int64>>,std::_Iterator_base0>>(unsigned __int64 const &,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned __int64>>,std::_Iterator_base0>)
0x180008938  cmp     rbx, rsi
0x18000893b  jnz     short loc_18000891E
0x18000893d  mov     rbx, [rsp+38h+arg_0]
0x180008942  mov     rsi, [rsp+38h+arg_8]
0x180008947  add     rsp, 30h
0x18000894b  pop     rdi
0x18000894c  retn
```
