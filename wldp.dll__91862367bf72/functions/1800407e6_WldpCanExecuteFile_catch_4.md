# WldpCanExecuteFile$catch$4

- ea: `0x1800407e6`
- end: `0x18004081f`
- name: `WldpCanExecuteFile$catch$4`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18002c520`

## string_xrefs

- `0x1800407fa`: `onecore\base\ngscb\wldp\dll\canexecute.cpp`

## pseudocode

```c
__int64 __fastcall WldpCanExecuteFile_catch_4(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 56) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 312),
                           (void *)0x211,
                           (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\canexecute.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800407e6  mov     [rsp+arg_8], rdx
0x1800407eb  push    rbp
0x1800407ec  sub     rsp, 30h
0x1800407f0  mov     rbp, rdx
0x1800407f3  mov     rcx, [rbp+138h]; this
0x1800407fa  lea     r8, aOnecoreBaseNgs_6; "onecore\\base\\ngscb\\wldp\\dll\\canexe"...
0x180040801  mov     edx, 211h; void *
0x180040806  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18004080b  mov     [rbp+38h], eax
0x18004080e  mov     rax, 0
0x180040818  add     rsp, 30h
0x18004081c  pop     rbp
0x18004081d  retn
```
