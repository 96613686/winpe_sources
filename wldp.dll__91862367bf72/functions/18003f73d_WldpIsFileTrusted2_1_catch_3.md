# _WldpIsFileTrusted2_::_1_::catch$3

- ea: `0x18003f73d`
- end: `0x18003f776`
- name: `_WldpIsFileTrusted2_::_1_::catch$3`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18002c520`

## string_xrefs

- `0x18003f751`: `onecore\base\ngscb\wldp\dll\filetrust.cpp`

## pseudocode

```c
__int64 __fastcall WldpIsFileTrusted2_::_1_::catch_3(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 68) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 520),
                           (void *)0x6ED,
                           (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\filetrust.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18003f73d  mov     [rsp+arg_8], rdx
0x18003f742  push    rbp
0x18003f743  sub     rsp, 40h
0x18003f747  mov     rbp, rdx
0x18003f74a  mov     rcx, [rbp+208h]; this
0x18003f751  lea     r8, aOnecoreBaseNgs_4; "onecore\\base\\ngscb\\wldp\\dll\\filetr"...
0x18003f758  mov     edx, 6EDh; void *
0x18003f75d  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18003f762  mov     [rbp+44h], eax
0x18003f765  mov     rax, 0
0x18003f76f  add     rsp, 40h
0x18003f773  pop     rbp
0x18003f774  retn
```
