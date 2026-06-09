# __lambda_ecc77f3a22ba66689a70fd4c73bb93c9_::operator()_::_1_::catch$1

- ea: `0x140027bb4`
- end: `0x140027be8`
- name: `__lambda_ecc77f3a22ba66689a70fd4c73bb93c9_::operator()_::_1_::catch$1`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400210cc`

## string_xrefs

- `0x140027bc5`: `enduser\ezap\easeofaccess\accessibilitydialog\accessibilitydialog.cpp`

## pseudocode

```c
__int64 __fastcall _lambda_ecc77f3a22ba66689a70fd4c73bb93c9_::operator()_::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 40),
    (void *)0x264,
    (unsigned int)"enduser\\ezap\\easeofaccess\\accessibilitydialog\\accessibilitydialog.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x140027bb4  mov     [rsp+arg_8], rdx
0x140027bb9  push    rbp
0x140027bba  sub     rsp, 20h
0x140027bbe  mov     rbp, rdx
0x140027bc1  mov     rcx, [rbp+28h]; this
0x140027bc5  lea     r8, aEnduserEzapEas_0; "enduser\\ezap\\easeofaccess\\accessibil"...
0x140027bcc  mov     edx, 264h; void *
0x140027bd1  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x140027bd6  nop
0x140027bd7  mov     rax, 0
0x140027be1  add     rsp, 20h
0x140027be5  pop     rbp
0x140027be6  retn
```
