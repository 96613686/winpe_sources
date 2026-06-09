# __lambda_9e243cd42256cb2016ea3fc542f067b8_::operator()_::_1_::catch$1

- ea: `0x140027b7a`
- end: `0x140027bae`
- name: `__lambda_9e243cd42256cb2016ea3fc542f067b8_::operator()_::_1_::catch$1`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400210cc`

## string_xrefs

- `0x140027b8b`: `enduser\ezap\easeofaccess\accessibilitydialog\accessibilitydialog.cpp`

## pseudocode

```c
__int64 __fastcall _lambda_9e243cd42256cb2016ea3fc542f067b8_::operator()_::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 40),
    (void *)0x272,
    (unsigned int)"enduser\\ezap\\easeofaccess\\accessibilitydialog\\accessibilitydialog.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x140027b7a  mov     [rsp+arg_8], rdx
0x140027b7f  push    rbp
0x140027b80  sub     rsp, 20h
0x140027b84  mov     rbp, rdx
0x140027b87  mov     rcx, [rbp+28h]; this
0x140027b8b  lea     r8, aEnduserEzapEas_0; "enduser\\ezap\\easeofaccess\\accessibil"...
0x140027b92  mov     edx, 272h; void *
0x140027b97  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x140027b9c  nop
0x140027b9d  mov     rax, 0
0x140027ba7  add     rsp, 20h
0x140027bab  pop     rbp
0x140027bac  retn
```
