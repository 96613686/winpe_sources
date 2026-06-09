# __lambda_29cd49ae10851c4c5ece1756c35aa1ca_::operator()_::_1_::catch$1

- ea: `0x140027b06`
- end: `0x140027b3a`
- name: `__lambda_29cd49ae10851c4c5ece1756c35aa1ca_::operator()_::_1_::catch$1`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400210cc`

## string_xrefs

- `0x140027b17`: `enduser\ezap\easeofaccess\accessibilitydialog\accessibilitydialog.cpp`

## pseudocode

```c
__int64 __fastcall _lambda_29cd49ae10851c4c5ece1756c35aa1ca_::operator()_::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 40),
    (void *)0x280,
    (unsigned int)"enduser\\ezap\\easeofaccess\\accessibilitydialog\\accessibilitydialog.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x140027b06  mov     [rsp+arg_8], rdx
0x140027b0b  push    rbp
0x140027b0c  sub     rsp, 20h
0x140027b10  mov     rbp, rdx
0x140027b13  mov     rcx, [rbp+28h]; this
0x140027b17  lea     r8, aEnduserEzapEas_0; "enduser\\ezap\\easeofaccess\\accessibil"...
0x140027b1e  mov     edx, 280h; void *
0x140027b23  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x140027b28  nop
0x140027b29  mov     rax, 0
0x140027b33  add     rsp, 20h
0x140027b37  pop     rbp
0x140027b38  retn
```
