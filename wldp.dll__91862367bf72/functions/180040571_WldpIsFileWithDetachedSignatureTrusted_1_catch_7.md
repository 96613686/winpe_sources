# _WldpIsFileWithDetachedSignatureTrusted_::_1_::catch$7

- ea: `0x180040571`
- end: `0x1800405aa`
- name: `_WldpIsFileWithDetachedSignatureTrusted_::_1_::catch$7`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18002c520`

## string_xrefs

- `0x180040585`: `onecore\base\ngscb\wldp\dll\filetrust.cpp`

## pseudocode

```c
__int64 __fastcall WldpIsFileWithDetachedSignatureTrusted_::_1_::catch_7(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 64) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 472),
                           (void *)0x801,
                           (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\filetrust.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180040571  mov     [rsp+arg_8], rdx
0x180040576  push    rbp
0x180040577  sub     rsp, 40h
0x18004057b  mov     rbp, rdx
0x18004057e  mov     rcx, [rbp+1D8h]; this
0x180040585  lea     r8, aOnecoreBaseNgs_4; "onecore\\base\\ngscb\\wldp\\dll\\filetr"...
0x18004058c  mov     edx, 801h; void *
0x180040591  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180040596  mov     [rbp+40h], eax
0x180040599  mov     rax, 0
0x1800405a3  add     rsp, 40h
0x1800405a7  pop     rbp
0x1800405a8  retn
```
