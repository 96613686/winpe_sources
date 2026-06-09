# _XamlUI::OnLayoutUpdated_::_1_::catch$11

- ea: `0x14002805b`
- end: `0x14002808f`
- name: `_XamlUI::OnLayoutUpdated_::_1_::catch$11`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400210cc`

## string_xrefs

- `0x14002806c`: `enduser\ezap\xamlcommon\xamlui.cpp`

## pseudocode

```c
__int64 __fastcall XamlUI::OnLayoutUpdated_::_1_::catch_11(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 72),
    (void *)0xA6,
    (unsigned int)"enduser\\ezap\\xamlcommon\\xamlui.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x14002805b  mov     [rsp+arg_8], rdx
0x140028060  push    rbp
0x140028061  sub     rsp, 20h
0x140028065  mov     rbp, rdx
0x140028068  mov     rcx, [rbp+48h]; this
0x14002806c  lea     r8, aEnduserEzapXam; "enduser\\ezap\\xamlcommon\\xamlui.cpp"
0x140028073  mov     edx, 0A6h; void *
0x140028078  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x14002807d  nop
0x14002807e  mov     rax, 0
0x140028088  add     rsp, 20h
0x14002808c  pop     rbp
0x14002808d  retn
```
