# _Windows::Internal::Notifications::CToastActivator_Protocol::CanActivate_::_1_::catch$0

- ea: `0x18003148c`
- end: `0x1800314c2`
- name: `_Windows::Internal::Notifications::CToastActivator_Protocol::CanActivate_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180023b84`

## string_xrefs

- `0x18003149d`: `onecoreuap\base\diagnosis\platform\notifications\client\src\ctoastactivator_protocol.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Notifications::CToastActivator_Protocol::CanActivate_::_1_::catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 72),
                           (void *)0xA7,
                           (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\src\\ctoastactiva"
                                         "tor_protocol.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18003148c  mov     [rsp+arg_8], rdx
0x180031491  push    rbp
0x180031492  sub     rsp, 30h
0x180031496  mov     rbp, rdx
0x180031499  mov     rcx, [rbp+48h]; this
0x18003149d  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800314a4  mov     edx, 0A7h; void *
0x1800314a9  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800314ae  mov     [rbp+30h], eax
0x1800314b1  mov     rax, 0
0x1800314bb  add     rsp, 30h
0x1800314bf  pop     rbp
0x1800314c0  retn
```
