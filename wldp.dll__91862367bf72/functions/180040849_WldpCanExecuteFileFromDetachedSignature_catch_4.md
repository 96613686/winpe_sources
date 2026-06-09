# WldpCanExecuteFileFromDetachedSignature$catch$4

- ea: `0x180040849`
- end: `0x180040882`
- name: `WldpCanExecuteFileFromDetachedSignature$catch$4`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18002c520`

## string_xrefs

- `0x18004085d`: `onecore\base\ngscb\wldp\dll\canexecute.cpp`

## pseudocode

```c
__int64 __fastcall WldpCanExecuteFileFromDetachedSignature_catch_4(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 52) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 344),
                           (void *)0x35F,
                           (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\canexecute.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180040849  mov     [rsp+arg_8], rdx
0x18004084e  push    rbp
0x18004084f  sub     rsp, 30h
0x180040853  mov     rbp, rdx
0x180040856  mov     rcx, [rbp+158h]; this
0x18004085d  lea     r8, aOnecoreBaseNgs_6; "onecore\\base\\ngscb\\wldp\\dll\\canexe"...
0x180040864  mov     edx, 35Fh; void *
0x180040869  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18004086e  mov     [rbp+34h], eax
0x180040871  mov     rax, 0
0x18004087b  add     rsp, 30h
0x18004087f  pop     rbp
0x180040880  retn
```
