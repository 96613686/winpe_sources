# _WldpIsFileTrustedByConfigCi_::_1_::catch$10

- ea: `0x18003f81d`
- end: `0x18003f859`
- name: `_WldpIsFileTrustedByConfigCi_::_1_::catch$10`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18002c520`

## string_xrefs

- `0x18003f831`: `onecore\base\ngscb\wldp\dll\filetrust.cpp`

## pseudocode

```c
__int64 __fastcall WldpIsFileTrustedByConfigCi_::_1_::catch_10(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 152) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 584),
                            (void *)0x409,
                            (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\filetrust.cpp",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x18003f81d  mov     [rsp+arg_8], rdx
0x18003f822  push    rbp
0x18003f823  sub     rsp, 50h
0x18003f827  mov     rbp, rdx
0x18003f82a  mov     rcx, [rbp+248h]; this
0x18003f831  lea     r8, aOnecoreBaseNgs_4; "onecore\\base\\ngscb\\wldp\\dll\\filetr"...
0x18003f838  mov     edx, 409h; void *
0x18003f83d  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18003f842  mov     [rbp+98h], eax
0x18003f848  mov     rax, 0
0x18003f852  add     rsp, 50h
0x18003f856  pop     rbp
0x18003f857  retn
```
