# _Windows::Internal::Tethering::GetLoggedInUserSID_::_1_::catch$28

- ea: `0x1800323e0`
- end: `0x180032417`
- name: `_Windows::Internal::Tethering::GetLoggedInUserSID_::_1_::catch$28`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task`

## callees

- `0x18001a2d8`

## string_xrefs

- `0x1800323f4`: `onecoreuap\net\tethering\service\userutils.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Tethering::GetLoggedInUserSID_::_1_::catch_28(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 184),
    (void *)0x2F,
    (unsigned int)"onecoreuap\\net\\tethering\\service\\userutils.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x1800323e0  mov     [rsp+arg_8], rdx
0x1800323e5  push    rbp
0x1800323e6  sub     rsp, 20h
0x1800323ea  mov     rbp, rdx
0x1800323ed  mov     rcx, [rbp+0B8h]; this
0x1800323f4  lea     r8, aOnecoreuapNetT_1; "onecoreuap\\net\\tethering\\service\\us"...
0x1800323fb  mov     edx, 2Fh ; '/'; void *
0x180032400  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180032405  nop
0x180032406  mov     rax, 0
0x180032410  add     rsp, 20h
0x180032414  pop     rbp
0x180032415  retn
```
