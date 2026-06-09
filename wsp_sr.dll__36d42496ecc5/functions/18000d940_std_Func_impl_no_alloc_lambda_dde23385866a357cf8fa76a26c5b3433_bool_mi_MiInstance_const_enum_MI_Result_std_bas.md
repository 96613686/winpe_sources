# std::_Func_impl_no_alloc__lambda_dde23385866a357cf8fa76a26c5b3433__bool_mi::MiInstance_const_&_enum__MI_Result_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____const_&_mi::MiInstance_const_&_::_Delete_this

- ea: `0x18000d940`
- end: `0x18000d957`
- name: `std::_Func_impl_no_alloc__lambda_dde23385866a357cf8fa76a26c5b3433__bool_mi::MiInstance_const_&_enum__MI_Result_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____const_&_mi::MiInstance_const_&_::_Delete_this`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000570c`
- `0x18000d940`

## pseudocode

```c
void __fastcall std::_Func_impl_no_alloc__lambda_dde23385866a357cf8fa76a26c5b3433__bool_mi::MiInstance_const___enum__MI_Result_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____const___mi::MiInstance_const___::_Delete_this(
        void *a1,
        char a2)
{
  if ( a2 )
    std::_Deallocate<16>(a1, 0x38u);
}

```

## disassembly

```asm
0x18000d940  sub     rsp, 28h
0x18000d944  test    dl, dl
0x18000d946  jz      short loc_18000D952
0x18000d948  mov     edx, 38h ; '8'
0x18000d94d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000d952  add     rsp, 28h
0x18000d956  retn
```
