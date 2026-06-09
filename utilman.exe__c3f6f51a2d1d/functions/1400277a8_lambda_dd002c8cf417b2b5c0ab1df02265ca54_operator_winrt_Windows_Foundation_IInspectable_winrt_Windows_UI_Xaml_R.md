# __lambda_dd002c8cf417b2b5c0ab1df02265ca54_::operator()_winrt::Windows::Foundation::IInspectable_winrt::Windows::UI::Xaml::RoutedEventArgs__::_1_::catch$11

- ea: `0x1400277a8`
- end: `0x1400277dc`
- name: `__lambda_dd002c8cf417b2b5c0ab1df02265ca54_::operator()_winrt::Windows::Foundation::IInspectable_winrt::Windows::UI::Xaml::RoutedEventArgs__::_1_::catch$11`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400210cc`

## string_xrefs

- `0x1400277b9`: `enduser\ezap\easeofaccess\accessibilitydialog\accessibilitydialog.cpp`

## pseudocode

```c
__int64 __fastcall _lambda_dd002c8cf417b2b5c0ab1df02265ca54_::operator()_winrt::Windows::Foundation::IInspectable_winrt::Windows::UI::Xaml::RoutedEventArgs__::_1_::catch_11(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 72),
    (void *)0x2F4,
    (unsigned int)"enduser\\ezap\\easeofaccess\\accessibilitydialog\\accessibilitydialog.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x1400277a8  mov     [rsp+arg_8], rdx
0x1400277ad  push    rbp
0x1400277ae  sub     rsp, 20h
0x1400277b2  mov     rbp, rdx
0x1400277b5  mov     rcx, [rbp+48h]; this
0x1400277b9  lea     r8, aEnduserEzapEas_0; "enduser\\ezap\\easeofaccess\\accessibil"...
0x1400277c0  mov     edx, 2F4h; void *
0x1400277c5  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x1400277ca  nop
0x1400277cb  mov     rax, 0
0x1400277d5  add     rsp, 20h
0x1400277d9  pop     rbp
0x1400277da  retn
```
