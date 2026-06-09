# WldpCanExecuteStream$catch$2

- ea: `0x18004089a`
- end: `0x1800408d3`
- name: `WldpCanExecuteStream$catch$2`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18002c520`

## string_xrefs

- `0x1800408ae`: `onecore\base\ngscb\wldp\dll\canexecute.cpp`

## pseudocode

```c
__int64 __fastcall WldpCanExecuteStream_catch_2(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 216),
                           (void *)0x2D6,
                           (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\canexecute.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18004089a  mov     [rsp+arg_8], rdx
0x18004089f  push    rbp
0x1800408a0  sub     rsp, 30h
0x1800408a4  mov     rbp, rdx
0x1800408a7  mov     rcx, [rbp+0D8h]; this
0x1800408ae  lea     r8, aOnecoreBaseNgs_6; "onecore\\base\\ngscb\\wldp\\dll\\canexe"...
0x1800408b5  mov     edx, 2D6h; void *
0x1800408ba  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800408bf  mov     [rbp+30h], eax
0x1800408c2  mov     rax, 0
0x1800408cc  add     rsp, 30h
0x1800408d0  pop     rbp
0x1800408d1  retn
```
