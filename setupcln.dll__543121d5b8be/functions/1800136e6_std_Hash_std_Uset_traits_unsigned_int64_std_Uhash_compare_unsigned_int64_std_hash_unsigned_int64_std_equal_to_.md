# _std::_Hash_std::_Uset_traits_unsigned___int64_std::_Uhash_compare_unsigned___int64_std::hash_unsigned___int64__std::equal_to_unsigned___int64____std::allocator_unsigned___int64__0___::_Insert_unsigned___int64_const_&_std::_List_unchecked_const_iterator_std::_List_val_std::_List_simple_types_unsigned___int64____std::_Iterator_base0____::_1_::catch$1

- ea: `0x1800136e6`
- end: `0x18001370e`
- name: `_std::_Hash_std::_Uset_traits_unsigned___int64_std::_Uhash_compare_unsigned___int64_std::hash_unsigned___int64__std::equal_to_unsigned___int64____std::allocator_unsigned___int64__0___::_Insert_unsigned___int64_const_&_std::_List_unchecked_const_iterator_std::_List_val_std::_List_simple_types_unsigned___int64____std::_Iterator_base0____::_1_::catch$1`
- size: `40`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002b4c`
- `0x180008a54`

## pseudocode

```c
void __fastcall __noreturn std::_Hash_std::_Uset_traits_unsigned___int64_std::_Uhash_compare_unsigned___int64_std::hash_unsigned___int64__std::equal_to_unsigned___int64____std::allocator_unsigned___int64__0___::_Insert_unsigned___int64_const___std::_List_unchecked_const_iterator_std::_List_val_std::_List_simple_types_unsigned___int64____std::_Iterator_base0____::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  std::list<unsigned __int64>::erase(*(_QWORD *)(a2 + 80), a2 + 32, *(_QWORD *)(a2 + 104));
  throw;
}

```

## disassembly

```asm
0x1800136e6  mov     [rsp+arg_8], rdx
0x1800136eb  push    rbp
0x1800136ec  sub     rsp, 20h
0x1800136f0  mov     rbp, rdx
0x1800136f3  mov     r8, [rbp+68h]
0x1800136f7  lea     rdx, [rbp+20h]
0x1800136fb  mov     rcx, [rbp+50h]
0x1800136ff  call    ?erase@?$list@_KV?$allocator@_K@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@_K@std@@@std@@@2@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@_K@std@@@std@@@2@@Z; std::list<unsigned __int64>::erase(std::_List_const_iterator<std::_List_val<std::_List_simple_types<unsigned __int64>>>)
0x180013704  xor     edx, edx; pThrowInfo
0x180013706  xor     ecx, ecx; pExceptionObject
0x180013708  call    _CxxThrowException_0
```
