# _wil::details::CallAndHandleErrorsWithReturnType_void__lambda_6a73db1c48dc126f1224b85b4c582466__&_long_&_enum_Windows::Internal::Security::SmartScreen::AppReputationResult_0__::_1_::catch$0

- ea: `0x180028391`
- end: `0x1800283c7`
- name: `_wil::details::CallAndHandleErrorsWithReturnType_void__lambda_6a73db1c48dc126f1224b85b4c582466__&_long_&_enum_Windows::Internal::Security::SmartScreen::AppReputationResult_0__::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180018f60`

## string_xrefs

- `0x1800283a2`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
__int64 __fastcall wil::details::CallAndHandleErrorsWithReturnType_void__lambda_6a73db1c48dc126f1224b85b4c582466____long___enum_Windows::Internal::Security::SmartScreen::AppReputationResult_0__::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 64) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x58D,
                           (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180028391  mov     [rsp+arg_8], rdx
0x180028396  push    rbp
0x180028397  sub     rsp, 20h
0x18002839b  mov     rbp, rdx
0x18002839e  mov     rcx, [rbp+28h]; this
0x1800283a2  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800283a9  mov     edx, 58Dh; void *
0x1800283ae  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800283b3  mov     [rbp+40h], eax
0x1800283b6  mov     rax, 0
0x1800283c0  add     rsp, 20h
0x1800283c4  pop     rbp
0x1800283c5  retn
```
