# WldpCanExecuteBuffer$catch$2

- ea: `0x180040783`
- end: `0x1800407bc`
- name: `WldpCanExecuteBuffer$catch$2`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18002c520`

## string_xrefs

- `0x180040797`: `onecore\base\ngscb\wldp\dll\canexecute.cpp`

## pseudocode

```c
__int64 __fastcall WldpCanExecuteBuffer_catch_2(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 200),
                           (void *)0x274,
                           (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\canexecute.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180040783  mov     [rsp+arg_8], rdx
0x180040788  push    rbp
0x180040789  sub     rsp, 30h
0x18004078d  mov     rbp, rdx
0x180040790  mov     rcx, [rbp+0C8h]; this
0x180040797  lea     r8, aOnecoreBaseNgs_6; "onecore\\base\\ngscb\\wldp\\dll\\canexe"...
0x18004079e  mov     edx, 274h; void *
0x1800407a3  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800407a8  mov     [rbp+30h], eax
0x1800407ab  mov     rax, 0
0x1800407b5  add     rsp, 30h
0x1800407b9  pop     rbp
0x1800407ba  retn
```
