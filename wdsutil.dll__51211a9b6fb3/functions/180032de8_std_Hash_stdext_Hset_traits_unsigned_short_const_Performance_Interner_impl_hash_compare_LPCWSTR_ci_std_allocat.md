# _std::_Hash_stdext::_Hset_traits_unsigned_short_const___Performance::Interner::impl::hash_compare_LPCWSTR_ci_std::allocator_unsigned_short_const____0___::_Insert_unsigned_short_const___const_&_std::_List_unchecked_const_iterator_std::_List_val_std::_List_simple_types_unsigned_short_const______std::_Iterator_base0____::_1_::catch$14

- ea: `0x180032de8`
- end: `0x180032e0f`
- name: `_std::_Hash_stdext::_Hset_traits_unsigned_short_const___Performance::Interner::impl::hash_compare_LPCWSTR_ci_std::allocator_unsigned_short_const____0___::_Insert_unsigned_short_const___const_&_std::_List_unchecked_const_iterator_std::_List_val_std::_List_simple_types_unsigned_short_const______std::_Iterator_base0____::_1_::catch$14`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001d4c`
- `0x1800202dc`

## pseudocode

```c
void __fastcall __noreturn std::_Hash_stdext::_Hset_traits_unsigned_short_const___Performance::Interner::impl::hash_compare_LPCWSTR_ci_std::allocator_unsigned_short_const____0___::_Insert_unsigned_short_const___const___std::_List_unchecked_const_iterator_std::_List_val_std::_List_simple_types_unsigned_short_const______std::_Iterator_base0____::_1_::catch_14(
        __int64 a1,
        __int64 a2)
{
  std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Destroy_if_not_nil(
    *(_QWORD **)(a2 + 112),
    *(_QWORD ***)(a2 + 136));
  throw;
}

```

## disassembly

```asm
0x180032de8  mov     [rsp+arg_8], rdx
0x180032ded  push    rbp
0x180032dee  sub     rsp, 20h
0x180032df2  mov     rbp, rdx
0x180032df5  mov     rdx, [rbp+88h]
0x180032dfc  mov     rcx, [rbp+70h]
0x180032e00  call    ?_Destroy_if_not_nil@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Destroy_if_not_nil(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ushort const *>>,std::_Iterator_base0>)
0x180032e05  xor     edx, edx; pThrowInfo
0x180032e07  xor     ecx, ecx; pExceptionObject
0x180032e09  call    _CxxThrowException_0
```
