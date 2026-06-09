# _WldpIsFileTrustedBySbcp_::_1_::catch$6

- ea: `0x18003f527`
- end: `0x18003f560`
- name: `_WldpIsFileTrustedBySbcp_::_1_::catch$6`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18002c520`

## string_xrefs

- `0x18003f53b`: `onecore\base\ngscb\wldp\dll\filetrust.cpp`

## pseudocode

```c
__int64 __fastcall WldpIsFileTrustedBySbcp_::_1_::catch_6(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 112) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 248),
                            (void *)0x46C,
                            (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\filetrust.cpp",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x18003f527  mov     [rsp+arg_8], rdx
0x18003f52c  push    rbp
0x18003f52d  sub     rsp, 50h
0x18003f531  mov     rbp, rdx
0x18003f534  mov     rcx, [rbp+0F8h]; this
0x18003f53b  lea     r8, aOnecoreBaseNgs_4; "onecore\\base\\ngscb\\wldp\\dll\\filetr"...
0x18003f542  mov     edx, 46Ch; void *
0x18003f547  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18003f54c  mov     [rbp+70h], eax
0x18003f54f  mov     rax, 0
0x18003f559  add     rsp, 50h
0x18003f55d  pop     rbp
0x18003f55e  retn
```
