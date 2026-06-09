# _XamlUI::PreTranslateMessage_::_1_::catch$3

- ea: `0x1400280e1`
- end: `0x140028115`
- name: `_XamlUI::PreTranslateMessage_::_1_::catch$3`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400210cc`

## string_xrefs

- `0x1400280f2`: `enduser\ezap\xamlcommon\xamlui.cpp`

## pseudocode

```c
__int64 __fastcall XamlUI::PreTranslateMessage_::_1_::catch_3(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 40),
    (void *)0x14D,
    (unsigned int)"enduser\\ezap\\xamlcommon\\xamlui.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x1400280e1  mov     [rsp+arg_8], rdx
0x1400280e6  push    rbp
0x1400280e7  sub     rsp, 20h
0x1400280eb  mov     rbp, rdx
0x1400280ee  mov     rcx, [rbp+28h]; this
0x1400280f2  lea     r8, aEnduserEzapXam; "enduser\\ezap\\xamlcommon\\xamlui.cpp"
0x1400280f9  mov     edx, 14Dh; void *
0x1400280fe  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x140028103  nop
0x140028104  mov     rax, 0
0x14002810e  add     rsp, 20h
0x140028112  pop     rbp
0x140028113  retn
```
