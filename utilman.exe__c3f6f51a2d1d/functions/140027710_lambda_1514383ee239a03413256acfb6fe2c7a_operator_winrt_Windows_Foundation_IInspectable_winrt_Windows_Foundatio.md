# __lambda_1514383ee239a03413256acfb6fe2c7a_::operator()_winrt::Windows::Foundation::IInspectable_winrt::Windows::Foundation::IInspectable__::_1_::catch$1

- ea: `0x140027710`
- end: `0x140027744`
- name: `__lambda_1514383ee239a03413256acfb6fe2c7a_::operator()_winrt::Windows::Foundation::IInspectable_winrt::Windows::Foundation::IInspectable__::_1_::catch$1`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400210cc`

## string_xrefs

- `0x140027721`: `enduser\ezap\easeofaccess\accessibilitydialog\accessibilitydialog.cpp`

## pseudocode

```c
__int64 __fastcall _lambda_1514383ee239a03413256acfb6fe2c7a_::operator()_winrt::Windows::Foundation::IInspectable_winrt::Windows::Foundation::IInspectable__::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 40),
    (void *)0x2D4,
    (unsigned int)"enduser\\ezap\\easeofaccess\\accessibilitydialog\\accessibilitydialog.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x140027710  mov     [rsp+arg_8], rdx
0x140027715  push    rbp
0x140027716  sub     rsp, 20h
0x14002771a  mov     rbp, rdx
0x14002771d  mov     rcx, [rbp+28h]; this
0x140027721  lea     r8, aEnduserEzapEas_0; "enduser\\ezap\\easeofaccess\\accessibil"...
0x140027728  mov     edx, 2D4h; void *
0x14002772d  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x140027732  nop
0x140027733  mov     rax, 0
0x14002773d  add     rsp, 20h
0x140027741  pop     rbp
0x140027742  retn
```
