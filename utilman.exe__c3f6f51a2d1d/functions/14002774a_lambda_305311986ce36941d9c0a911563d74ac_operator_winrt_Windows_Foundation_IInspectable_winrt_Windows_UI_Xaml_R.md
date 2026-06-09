# __lambda_305311986ce36941d9c0a911563d74ac_::operator()_winrt::Windows::Foundation::IInspectable_winrt::Windows::UI::Xaml::RoutedEventArgs__::_1_::catch$1

- ea: `0x14002774a`
- end: `0x14002777e`
- name: `__lambda_305311986ce36941d9c0a911563d74ac_::operator()_winrt::Windows::Foundation::IInspectable_winrt::Windows::UI::Xaml::RoutedEventArgs__::_1_::catch$1`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400210cc`

## string_xrefs

- `0x14002775b`: `enduser\ezap\easeofaccess\accessibilitydialog\accessibilitydialog.cpp`

## pseudocode

```c
__int64 __fastcall _lambda_305311986ce36941d9c0a911563d74ac_::operator()_winrt::Windows::Foundation::IInspectable_winrt::Windows::UI::Xaml::RoutedEventArgs__::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 40),
    (void *)0x2E2,
    (unsigned int)"enduser\\ezap\\easeofaccess\\accessibilitydialog\\accessibilitydialog.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x14002774a  mov     [rsp+arg_8], rdx
0x14002774f  push    rbp
0x140027750  sub     rsp, 20h
0x140027754  mov     rbp, rdx
0x140027757  mov     rcx, [rbp+28h]; this
0x14002775b  lea     r8, aEnduserEzapEas_0; "enduser\\ezap\\easeofaccess\\accessibil"...
0x140027762  mov     edx, 2E2h; void *
0x140027767  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x14002776c  nop
0x14002776d  mov     rax, 0
0x140027777  add     rsp, 20h
0x14002777b  pop     rbp
0x14002777c  retn
```
