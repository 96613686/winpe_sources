# _WldpIsFileTrusted_::_1_::catch$2

- ea: `0x18003eed6`
- end: `0x18003ef0f`
- name: `_WldpIsFileTrusted_::_1_::catch$2`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18002c520`

## string_xrefs

- `0x18003eeea`: `onecore\base\ngscb\wldp\dll\filetrust.cpp`

## pseudocode

```c
__int64 __fastcall WldpIsFileTrusted_::_1_::catch_2(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 68) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 504),
                           (void *)0x5B7,
                           (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\filetrust.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18003eed6  mov     [rsp+arg_8], rdx
0x18003eedb  push    rbp
0x18003eedc  sub     rsp, 40h
0x18003eee0  mov     rbp, rdx
0x18003eee3  mov     rcx, [rbp+1F8h]; this
0x18003eeea  lea     r8, aOnecoreBaseNgs_4; "onecore\\base\\ngscb\\wldp\\dll\\filetr"...
0x18003eef1  mov     edx, 5B7h; void *
0x18003eef6  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18003eefb  mov     [rbp+44h], eax
0x18003eefe  mov     rax, 0
0x18003ef08  add     rsp, 40h
0x18003ef0c  pop     rbp
0x18003ef0d  retn
```
