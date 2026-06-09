# std::_Func_impl_no_alloc__lambda_8d049788fa098b2c5d15a099732ce30d__bool_mi::MiInstance_const_&_enum__MI_Result_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____const_&_mi::MiInstance_const_&_::_Copy

- ea: `0x1800214d0`
- end: `0x180021527`
- name: `std::_Func_impl_no_alloc__lambda_8d049788fa098b2c5d15a099732ce30d__bool_mi::MiInstance_const_&_enum__MI_Result_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____const_&_mi::MiInstance_const_&_::_Copy`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180005510`
- `0x1800205c0`
- `0x180020684`

## pseudocode

```c
_QWORD *__fastcall std::_Func_impl_no_alloc__lambda_8d049788fa098b2c5d15a099732ce30d__bool_mi::MiInstance_const___enum__MI_Result_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____const___mi::MiInstance_const___::_Copy(
        __int64 a1)
{
  _QWORD *v2; // rdi
  _QWORD *v4; // [rsp+30h] [rbp+8h] BYREF

  v2 = std::_Allocate<16,std::_Default_allocate_traits>(0x48u);
  v4 = v2;
  *v2 = &std::_Func_impl_no_alloc<_lambda_8d049788fa098b2c5d15a099732ce30d_,bool,mi::MiInstance const &,enum _MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable';
  std::function<bool (wvr::MSFT_WvrReplicationGroup const &)>::function<bool (wvr::MSFT_WvrReplicationGroup const &)>(
    v2 + 1,
    a1 + 8);
  v4 = 0;
  std::_Global_new_std::_Func_impl_no_alloc__lambda_f3c6453b5126a506d23099b113dcd4fd__bool_mi::MiInstance_const___enum__MI_Result_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____const___mi::MiInstance_const_____lambda_f3c6453b5126a506d23099b113dcd4fd____::_2_::_Guard_type::__Guard_type(&v4);
  return v2;
}

```

## disassembly

```asm
0x1800214d0  mov     [rsp+arg_8], rbx
0x1800214d5  push    rdi
0x1800214d6  sub     rsp, 20h
0x1800214da  mov     rbx, rcx
0x1800214dd  mov     ecx, 48h ; 'H'
0x1800214e2  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800214e7  mov     rdi, rax
0x1800214ea  mov     [rsp+28h+arg_0], rax
0x1800214ef  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_8d049788fa098b2c5d15a099732ce30d_@@_NAEBVMiInstance@mi@@W4_MI_Result@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_8d049788fa098b2c5d15a099732ce30d_,bool,mi::MiInstance const &,_MI_Result,std::wstring const &,mi::MiInstance const &>::`vftable'
0x1800214f6  mov     [rdi], rax
0x1800214f9  lea     rdx, [rbx+8]
0x1800214fd  lea     rcx, [rdi+8]
0x180021501  call    ??0?$function@$$A6A_NAEBVMSFT_WvrReplicationGroup@wvr@@@Z@std@@QEAA@AEBV01@@Z; std::function<bool (wvr::MSFT_WvrReplicationGroup const &)>::function<bool (wvr::MSFT_WvrReplicationGroup const &)>(std::function<bool (wvr::MSFT_WvrReplicationGroup const &)> const &)
0x180021506  mov     [rsp+28h+arg_0], 0
0x18002150f  lea     rcx, [rsp+28h+arg_0]
0x180021514  call    _std___Global_new_std___Func_impl_no_alloc__lambda_f3c6453b5126a506d23099b113dcd4fd__bool_mi__MiInstance_const___enum__MI_Result_std__basic_string_wchar_t_std__char_traits_wchar_t__std__allocator_wchar_t____const___mi__MiInstance_const_____lambda_f3c6453b5126a506d23099b113dcd4fd_______2____Guard_type____Guard_type
0x180021519  mov     rax, rdi
0x18002151c  mov     rbx, [rsp+28h+arg_8]
0x180021521  add     rsp, 20h
0x180021525  pop     rdi
0x180021526  retn
```
