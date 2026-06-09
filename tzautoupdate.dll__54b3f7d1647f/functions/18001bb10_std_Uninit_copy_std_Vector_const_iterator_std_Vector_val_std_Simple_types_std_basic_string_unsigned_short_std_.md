# _std::_Uninit_copy_std::_Vector_const_iterator_std::_Vector_val_std::_Simple_types_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short__________std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short________::_1_::catch$0

- ea: `0x18001bb10`
- end: `0x18001bb40`
- name: `_std::_Uninit_copy_std::_Vector_const_iterator_std::_Vector_val_std::_Simple_types_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short__________std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short________::_1_::catch$0`
- size: `48`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180002960`
- `0x18000dc10`
- `0x18001bb10`

## pseudocode

```c
void __fastcall __noreturn std::_Uninit_copy_std::_Vector_const_iterator_std::_Vector_val_std::_Simple_types_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short__________std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short________::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  __int64 i; // rbx

  for ( i = *(_QWORD *)(a2 + 72); i != *(_QWORD *)(a2 + 64); i += 32 )
    std::wstring::`scalar deleting destructor'(i);
  throw;
}

```

## disassembly

```asm
0x18001bb10  mov     [rsp+arg_8], rdx
0x18001bb15  push    rbx
0x18001bb16  push    rbp
0x18001bb17  sub     rsp, 28h
0x18001bb1b  mov     rbp, rdx
0x18001bb1e  mov     rbx, [rbp+48h]
0x18001bb22  jmp     short loc_18001BB30
0x18001bb24  mov     rcx, rbx
0x18001bb27  call    ??_G?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAPEAXI@Z; std::wstring::`scalar deleting destructor'(uint)
0x18001bb2c  add     rbx, 20h ; ' '
0x18001bb30  cmp     rbx, [rbp+40h]
0x18001bb34  jnz     short loc_18001BB24
0x18001bb36  xor     edx, edx; pThrowInfo
0x18001bb38  xor     ecx, ecx; pExceptionObject
0x18001bb3a  call    _CxxThrowException_0
```
