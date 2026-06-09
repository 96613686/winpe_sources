# _XamlUI::ResizeParentWindowToFitXamlContent_::_1_::catch$1

- ea: `0x14002812d`
- end: `0x140028164`
- name: `_XamlUI::ResizeParentWindowToFitXamlContent_::_1_::catch$1`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400210cc`

## string_xrefs

- `0x140028141`: `enduser\ezap\xamlcommon\xamlui.cpp`

## pseudocode

```c
__int64 __fastcall XamlUI::ResizeParentWindowToFitXamlContent_::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 312),
    (void *)0x12A,
    (unsigned int)"enduser\\ezap\\xamlcommon\\xamlui.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x14002812d  mov     [rsp+arg_8], rdx
0x140028132  push    rbp
0x140028133  sub     rsp, 40h
0x140028137  mov     rbp, rdx
0x14002813a  mov     rcx, [rbp+138h]; this
0x140028141  lea     r8, aEnduserEzapXam; "enduser\\ezap\\xamlcommon\\xamlui.cpp"
0x140028148  mov     edx, 12Ah; void *
0x14002814d  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x140028152  nop
0x140028153  mov     rax, 0
0x14002815d  add     rsp, 40h
0x140028161  pop     rbp
0x140028162  retn
```
