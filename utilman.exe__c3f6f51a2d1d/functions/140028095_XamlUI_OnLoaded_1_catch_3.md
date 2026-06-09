# _XamlUI::OnLoaded_::_1_::catch$3

- ea: `0x140028095`
- end: `0x1400280c9`
- name: `_XamlUI::OnLoaded_::_1_::catch$3`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400210cc`

## string_xrefs

- `0x1400280a6`: `enduser\ezap\xamlcommon\xamlui.cpp`

## pseudocode

```c
__int64 __fastcall XamlUI::OnLoaded_::_1_::catch_3(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 56),
    (void *)0x97,
    (unsigned int)"enduser\\ezap\\xamlcommon\\xamlui.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x140028095  mov     [rsp+arg_8], rdx
0x14002809a  push    rbp
0x14002809b  sub     rsp, 20h
0x14002809f  mov     rbp, rdx
0x1400280a2  mov     rcx, [rbp+38h]; this
0x1400280a6  lea     r8, aEnduserEzapXam; "enduser\\ezap\\xamlcommon\\xamlui.cpp"
0x1400280ad  mov     edx, 97h; void *
0x1400280b2  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x1400280b7  nop
0x1400280b8  mov     rax, 0
0x1400280c2  add     rsp, 20h
0x1400280c6  pop     rbp
0x1400280c7  retn
```
