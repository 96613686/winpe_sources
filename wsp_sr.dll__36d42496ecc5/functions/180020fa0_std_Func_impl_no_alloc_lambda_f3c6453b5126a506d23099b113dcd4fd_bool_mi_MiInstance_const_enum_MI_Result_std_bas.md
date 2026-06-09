# std::_Func_impl_no_alloc__lambda_f3c6453b5126a506d23099b113dcd4fd__bool_mi::MiInstance_const_&_enum__MI_Result_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____const_&_mi::MiInstance_const_&_::_Delete_this

- ea: `0x180020fa0`
- end: `0x180020fd4`
- name: `std::_Func_impl_no_alloc__lambda_f3c6453b5126a506d23099b113dcd4fd__bool_mi::MiInstance_const_&_enum__MI_Result_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____const_&_mi::MiInstance_const_&_::_Delete_this`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000570c`
- `0x18002064c`
- `0x180020fa0`

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
0x180020fa0  mov     [rsp+arg_0], rbx
0x180020fa5  push    rdi
0x180020fa6  sub     rsp, 20h
0x180020faa  mov     rdi, rcx
0x180020fad  mov     bl, dl
0x180020faf  add     rcx, 8
0x180020fb3  call    _lambda_f3c6453b5126a506d23099b113dcd4fd_____lambda_f3c6453b5126a506d23099b113dcd4fd_
0x180020fb8  test    bl, bl
0x180020fba  jz      short loc_180020FC9
0x180020fbc  mov     edx, 48h ; 'H'
0x180020fc1  mov     rcx, rdi
0x180020fc4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180020fc9  mov     rbx, [rsp+28h+arg_0]
0x180020fce  add     rsp, 20h
0x180020fd2  pop     rdi
0x180020fd3  retn
```
