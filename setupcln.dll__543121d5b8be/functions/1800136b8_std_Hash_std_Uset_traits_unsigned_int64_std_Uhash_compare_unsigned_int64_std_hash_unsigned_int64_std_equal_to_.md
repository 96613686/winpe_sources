# _std::_Hash_std::_Uset_traits_unsigned___int64_std::_Uhash_compare_unsigned___int64_std::hash_unsigned___int64__std::equal_to_unsigned___int64____std::allocator_unsigned___int64__0___::_Insert_unsigned___int64_const_&_std::_List_unchecked_const_iterator_std::_List_val_std::_List_simple_types_unsigned___int64____std::_Iterator_base0____::_1_::catch$0

- ea: `0x1800136b8`
- end: `0x1800136e0`
- name: `_std::_Hash_std::_Uset_traits_unsigned___int64_std::_Uhash_compare_unsigned___int64_std::hash_unsigned___int64__std::equal_to_unsigned___int64____std::allocator_unsigned___int64__0___::_Insert_unsigned___int64_const_&_std::_List_unchecked_const_iterator_std::_List_val_std::_List_simple_types_unsigned___int64____std::_Iterator_base0____::_1_::catch$0`
- size: `40`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002b4c`
- `0x1800089c8`

## pseudocode

```c
void __fastcall __noreturn std::_Hash_std::_Uset_traits_unsigned___int64_std::_Uhash_compare_unsigned___int64_std::hash_unsigned___int64__std::equal_to_unsigned___int64____std::allocator_unsigned___int64__0___::_Insert_unsigned___int64_const___std::_List_unchecked_const_iterator_std::_List_val_std::_List_simple_types_unsigned___int64____std::_Iterator_base0____::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::erase(
    *(_QWORD **)(a2 + 80),
    (_QWORD *)(a2 + 32),
    *(_QWORD *)(a2 + 104));
  throw;
}

```

## disassembly

```asm
0x1800136b8  mov     [rsp+arg_8], rdx
0x1800136bd  push    rbp
0x1800136be  sub     rsp, 20h
0x1800136c2  mov     rbp, rdx
0x1800136c5  mov     r8, [rbp+68h]
0x1800136c9  lea     rdx, [rbp+20h]
0x1800136cd  mov     rcx, [rbp+50h]
0x1800136d1  call    ?erase@?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@QEAA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@_K@std@@@std@@@2@V32@@Z; std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::erase(std::_List_const_iterator<std::_List_val<std::_List_simple_types<unsigned __int64>>>)
0x1800136d6  xor     edx, edx; pThrowInfo
0x1800136d8  xor     ecx, ecx; pExceptionObject
0x1800136da  call    _CxxThrowException_0
```
