# _std::_Uninit_move_std::_List_unchecked_const_iterator_std::_List_val_std::_List_simple_types_unsigned___int64____std::_Iterator_base0____std::_List_unchecked_const_iterator_std::_List_val_std::_List_simple_types_unsigned___int64____std::_Iterator_base0____std::_Wrap_alloc_std::allocator_std::_List_unchecked_const_iterator_std::_List_val_std::_List_simple_types_unsigned___int64____std::_Iterator_base0______std::_List_unchecked_const_iterator_std::_List_val_std::_List_simple_types_unsigned___int64____std::_Iterator_base0____::_1_::catch$0

- ea: `0x18001369b`
- end: `0x1800136b2`
- name: `_std::_Uninit_move_std::_List_unchecked_const_iterator_std::_List_val_std::_List_simple_types_unsigned___int64____std::_Iterator_base0____std::_List_unchecked_const_iterator_std::_List_val_std::_List_simple_types_unsigned___int64____std::_Iterator_base0____std::_Wrap_alloc_std::allocator_std::_List_unchecked_const_iterator_std::_List_val_std::_List_simple_types_unsigned___int64____std::_Iterator_base0______std::_List_unchecked_const_iterator_std::_List_val_std::_List_simple_types_unsigned___int64____std::_Iterator_base0____::_1_::catch$0`
- size: `23`
- prototype: `void __noreturn()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002b4c`

## pseudocode

```c
void __noreturn std::_Uninit_move_std::_List_unchecked_const_iterator_std::_List_val_std::_List_simple_types_unsigned___int64____std::_Iterator_base0____std::_List_unchecked_const_iterator_std::_List_val_std::_List_simple_types_unsigned___int64____std::_Iterator_base0____std::_Wrap_alloc_std::allocator_std::_List_unchecked_const_iterator_std::_List_val_std::_List_simple_types_unsigned___int64____std::_Iterator_base0______std::_List_unchecked_const_iterator_std::_List_val_std::_List_simple_types_unsigned___int64____std::_Iterator_base0____::_1_::catch_0()
{
  throw;
}

```

## disassembly

```asm
0x18001369b  mov     [rsp+arg_8], rdx
0x1800136a0  push    rbp
0x1800136a1  sub     rsp, 20h
0x1800136a5  mov     rbp, rdx
0x1800136a8  xor     edx, edx; pThrowInfo
0x1800136aa  xor     ecx, ecx; pExceptionObject
0x1800136ac  call    _CxxThrowException_0
```
