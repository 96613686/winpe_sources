# std::_Func_impl_no_alloc__lambda_f3c6453b5126a506d23099b113dcd4fd__bool_mi::MiInstance_const_&_enum__MI_Result_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____const_&_mi::MiInstance_const_&_::_Delete_this

- ea: `0x180021100`
- end: `0x180021135`
- name: `std::_Func_impl_no_alloc__lambda_f3c6453b5126a506d23099b113dcd4fd__bool_mi::MiInstance_const_&_enum__MI_Result_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____const_&_mi::MiInstance_const_&_::_Delete_this`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000573c`
- `0x1800207a0`
- `0x180021100`

## pseudocode

```c
void __fastcall std::_Func_impl_no_alloc__lambda_f3c6453b5126a506d23099b113dcd4fd__bool_mi::MiInstance_const___enum__MI_Result_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____const___mi::MiInstance_const___::_Delete_this(
        char *a1,
        char a2)
{
  lambda_f3c6453b5126a506d23099b113dcd4fd_::__lambda_f3c6453b5126a506d23099b113dcd4fd_(a1 + 8);
  if ( a2 )
    std::_Deallocate<16>(a1, 0x48u);
}

```

## disassembly

```asm
0x180021100  mov     [rsp+arg_0], rbx
0x180021105  push    rdi
0x180021106  sub     rsp, 20h
0x18002110a  mov     rdi, rcx
0x18002110d  mov     bl, dl
0x18002110f  add     rcx, 8
0x180021113  call    _lambda_f3c6453b5126a506d23099b113dcd4fd_____lambda_f3c6453b5126a506d23099b113dcd4fd_
0x180021118  test    bl, bl
0x18002111a  jz      short loc_180021129
0x18002111c  mov     edx, 48h ; 'H'
0x180021121  mov     rcx, rdi
0x180021124  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180021129  mov     rbx, [rsp+28h+arg_0]
0x18002112e  add     rsp, 20h
0x180021132  pop     rdi
0x180021133  retn
```
