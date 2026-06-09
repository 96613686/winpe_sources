# __lambda_0677d72bbab79ba89ea6fa9c9a9112cb_::operator()_winrt::Windows::Foundation::IInspectable_winrt::Windows::Foundation::IInspectable__::_1_::catch$1

- ea: `0x1400276c4`
- end: `0x1400276f8`
- name: `__lambda_0677d72bbab79ba89ea6fa9c9a9112cb_::operator()_winrt::Windows::Foundation::IInspectable_winrt::Windows::Foundation::IInspectable__::_1_::catch$1`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400210cc`

## string_xrefs

- `0x1400276d5`: `enduser\ezap\easeofaccess\accessibilitydialog\accessibilitydialog.cpp`

## pseudocode

```c
__int64 __fastcall _lambda_0677d72bbab79ba89ea6fa9c9a9112cb_::operator()_winrt::Windows::Foundation::IInspectable_winrt::Windows::Foundation::IInspectable__::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 40),
    (void *)0x2C6,
    (unsigned int)"enduser\\ezap\\easeofaccess\\accessibilitydialog\\accessibilitydialog.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x1400276c4  mov     [rsp+arg_8], rdx
0x1400276c9  push    rbp
0x1400276ca  sub     rsp, 20h
0x1400276ce  mov     rbp, rdx
0x1400276d1  mov     rcx, [rbp+28h]; this
0x1400276d5  lea     r8, aEnduserEzapEas_0; "enduser\\ezap\\easeofaccess\\accessibil"...
0x1400276dc  mov     edx, 2C6h; void *
0x1400276e1  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x1400276e6  nop
0x1400276e7  mov     rax, 0
0x1400276f1  add     rsp, 20h
0x1400276f5  pop     rbp
0x1400276f6  retn
```
