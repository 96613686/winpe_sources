# _std::_Hash_stdext::_Hset_traits_unsigned_short_const___Performance::Interner::impl::hash_compare_LPCWSTR_ci_std::allocator_unsigned_short_const____0___::_Insert_unsigned_short_const___const_&_std::_List_unchecked_const_iterator_std::_List_val_std::_List_simple_types_unsigned_short_const______std::_Iterator_base0____::_1_::catch$13

- ea: `0x180032e0f`
- end: `0x180032e46`
- name: `_std::_Hash_stdext::_Hset_traits_unsigned_short_const___Performance::Interner::impl::hash_compare_LPCWSTR_ci_std::allocator_unsigned_short_const____0___::_Insert_unsigned_short_const___const_&_std::_List_unchecked_const_iterator_std::_List_val_std::_List_simple_types_unsigned_short_const______std::_Iterator_base0____::_1_::catch$13`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001d4c`
- `0x1800206ac`
- `0x180020768`

## pseudocode

```c
void __fastcall __noreturn std::_Hash_stdext::_Hset_traits_unsigned_short_const___Performance::Interner::impl::hash_compare_LPCWSTR_ci_std::allocator_unsigned_short_const____0___::_Insert_unsigned_short_const___const___std::_List_unchecked_const_iterator_std::_List_val_std::_List_simple_types_unsigned_short_const______std::_Iterator_base0____::_1_::catch_13(
        __int64 a1,
        __int64 a2)
{
  wint_t ***iter; // rax

  iter = (wint_t ***)std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Make_iter(
                       a1,
                       a2 + 40,
                       *(_QWORD *)(a2 + 136));
  std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::erase(
    *(wint_t ***)(a2 + 112),
    (wint_t **)(a2 + 48),
    *iter);
  throw;
}

```

## disassembly

```asm
0x180032e0f  mov     [rsp+arg_8], rdx
0x180032e14  push    rbp
0x180032e15  sub     rsp, 20h
0x180032e19  mov     rbp, rdx
0x180032e1c  mov     r8, [rbp+88h]
0x180032e23  lea     rdx, [rbp+28h]
0x180032e27  call    ?_Make_iter@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@QEBA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@@2@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Make_iter(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ushort const *>>,std::_Iterator_base0>)
0x180032e2c  mov     r8, [rax]
0x180032e2f  lea     rdx, [rbp+30h]
0x180032e33  mov     rcx, [rbp+70h]
0x180032e37  call    ?erase@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@QEAA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@@2@V32@@Z; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::erase(std::_List_const_iterator<std::_List_val<std::_List_simple_types<ushort const *>>>)
0x180032e3c  xor     edx, edx; pThrowInfo
0x180032e3e  xor     ecx, ecx; pExceptionObject
0x180032e40  call    _CxxThrowException_0
```
