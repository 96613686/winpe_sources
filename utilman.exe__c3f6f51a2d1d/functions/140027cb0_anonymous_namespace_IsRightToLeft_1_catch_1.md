# __anonymous_namespace_::IsRightToLeft_::_1_::catch$1

- ea: `0x140027cb0`
- end: `0x140027ce4`
- name: `__anonymous_namespace_::IsRightToLeft_::_1_::catch$1`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400210cc`

## string_xrefs

- `0x140027cc1`: `enduser\ezap\easeofaccess\accessibilitydialog\accessibilitydialog.cpp`

## pseudocode

```c
__int64 __fastcall _anonymous_namespace_::IsRightToLeft_::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 56),
    (void *)0x85,
    (unsigned int)"enduser\\ezap\\easeofaccess\\accessibilitydialog\\accessibilitydialog.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x140027cb0  mov     [rsp+arg_8], rdx
0x140027cb5  push    rbp
0x140027cb6  sub     rsp, 20h
0x140027cba  mov     rbp, rdx
0x140027cbd  mov     rcx, [rbp+38h]; this
0x140027cc1  lea     r8, aEnduserEzapEas_0; "enduser\\ezap\\easeofaccess\\accessibil"...
0x140027cc8  mov     edx, 85h; void *
0x140027ccd  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x140027cd2  nop
0x140027cd3  mov     rax, 0
0x140027cdd  add     rsp, 20h
0x140027ce1  pop     rbp
0x140027ce2  retn
```
