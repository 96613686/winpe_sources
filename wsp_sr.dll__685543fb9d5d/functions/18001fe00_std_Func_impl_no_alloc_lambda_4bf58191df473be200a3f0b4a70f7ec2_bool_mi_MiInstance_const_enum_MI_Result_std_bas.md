# std::_Func_impl_no_alloc__lambda_4bf58191df473be200a3f0b4a70f7ec2__bool_mi::MiInstance_const_&_enum__MI_Result_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____const_&_mi::MiInstance_const_&_::_Delete_this

- ea: `0x18001fe00`
- end: `0x18001fe18`
- name: `std::_Func_impl_no_alloc__lambda_4bf58191df473be200a3f0b4a70f7ec2__bool_mi::MiInstance_const_&_enum__MI_Result_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____const_&_mi::MiInstance_const_&_::_Delete_this`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000573c`
- `0x18001fe00`

## pseudocode

```c
void __fastcall std::_Func_impl_no_alloc__lambda_4bf58191df473be200a3f0b4a70f7ec2__bool_mi::MiInstance_const___enum__MI_Result_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____const___mi::MiInstance_const___::_Delete_this(
        void *a1,
        char a2)
{
  if ( a2 )
    std::_Deallocate<16>(a1, 0x10u);
}

```

## disassembly

```asm
0x18001fe00  sub     rsp, 28h
0x18001fe04  test    dl, dl
0x18001fe06  jz      short loc_18001FE12
0x18001fe08  mov     edx, 10h
0x18001fe0d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001fe12  add     rsp, 28h
0x18001fe16  retn
```
