# _XamlUI::_XamlUI_::_1_::catch$10

- ea: `0x140027f2c`
- end: `0x140027f60`
- name: `_XamlUI::_XamlUI_::_1_::catch$10`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400210cc`

## string_xrefs

- `0x140027f3d`: `enduser\ezap\xamlcommon\xamlui.cpp`

## pseudocode

```c
__int64 __fastcall XamlUI::_XamlUI_::_1_::catch_10(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 40),
    (void *)0x6C,
    (unsigned int)"enduser\\ezap\\xamlcommon\\xamlui.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x140027f2c  mov     [rsp+arg_8], rdx
0x140027f31  push    rbp
0x140027f32  sub     rsp, 20h
0x140027f36  mov     rbp, rdx
0x140027f39  mov     rcx, [rbp+28h]; this
0x140027f3d  lea     r8, aEnduserEzapXam; "enduser\\ezap\\xamlcommon\\xamlui.cpp"
0x140027f44  mov     edx, 6Ch ; 'l'; void *
0x140027f49  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x140027f4e  nop
0x140027f4f  mov     rax, 0
0x140027f59  add     rsp, 20h
0x140027f5d  pop     rbp
0x140027f5e  retn
```
