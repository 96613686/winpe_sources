# __lambda_42e2fe3f81fbc7b11f6fa0537a423252_::operator()_::_1_::catch$1

- ea: `0x140027b40`
- end: `0x140027b74`
- name: `__lambda_42e2fe3f81fbc7b11f6fa0537a423252_::operator()_::_1_::catch$1`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400210cc`

## string_xrefs

- `0x140027b51`: `enduser\ezap\easeofaccess\accessibilitydialog\accessibilitydialog.cpp`

## pseudocode

```c
__int64 __fastcall _lambda_42e2fe3f81fbc7b11f6fa0537a423252_::operator()_::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 40),
    (void *)0x2B8,
    (unsigned int)"enduser\\ezap\\easeofaccess\\accessibilitydialog\\accessibilitydialog.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x140027b40  mov     [rsp+arg_8], rdx
0x140027b45  push    rbp
0x140027b46  sub     rsp, 20h
0x140027b4a  mov     rbp, rdx
0x140027b4d  mov     rcx, [rbp+28h]; this
0x140027b51  lea     r8, aEnduserEzapEas_0; "enduser\\ezap\\easeofaccess\\accessibil"...
0x140027b58  mov     edx, 2B8h; void *
0x140027b5d  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x140027b62  nop
0x140027b63  mov     rax, 0
0x140027b6d  add     rsp, 20h
0x140027b71  pop     rbp
0x140027b72  retn
```
