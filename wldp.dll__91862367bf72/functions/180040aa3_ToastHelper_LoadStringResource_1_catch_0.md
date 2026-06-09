# _ToastHelper::LoadStringResource_::_1_::catch$0

- ea: `0x180040aa3`
- end: `0x180040ad9`
- name: `_ToastHelper::LoadStringResource_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18002c520`

## string_xrefs

- `0x180040ab4`: `onecore\base\ngscb\wldp\dll\toasthelper.cpp`

## pseudocode

```c
__int64 __fastcall ToastHelper::LoadStringResource_::_1_::catch_0(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 64) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x46,
                           (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\toasthelper.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180040aa3  mov     [rsp+arg_8], rdx
0x180040aa8  push    rbp
0x180040aa9  sub     rsp, 20h
0x180040aad  mov     rbp, rdx
0x180040ab0  mov     rcx, [rbp+28h]; this
0x180040ab4  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\wldp\\dll\\toasth"...
0x180040abb  mov     edx, 46h ; 'F'; void *
0x180040ac0  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180040ac5  mov     [rbp+40h], eax
0x180040ac8  mov     rax, 0
0x180040ad2  add     rsp, 20h
0x180040ad6  pop     rbp
0x180040ad7  retn
```
