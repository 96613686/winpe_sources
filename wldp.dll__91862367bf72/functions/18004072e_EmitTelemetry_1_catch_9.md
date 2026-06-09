# _EmitTelemetry_::_1_::catch$9

- ea: `0x18004072e`
- end: `0x18004076b`
- name: `_EmitTelemetry_::_1_::catch$9`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800279e4`

## string_xrefs

- `0x180040745`: `onecore\base\ngscb\wldp\dll\canexecute.cpp`

## pseudocode

```c
__int64 __fastcall EmitTelemetry_::_1_::catch_9(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 600),
    (void *)0x131,
    (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\canexecute.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x18004072e  mov     [rsp+arg_8], rdx
0x180040733  push    rbp
0x180040734  sub     rsp, 0A0h
0x18004073b  mov     rbp, rdx
0x18004073e  mov     rcx, [rbp+258h]; this
0x180040745  lea     r8, aOnecoreBaseNgs_6; "onecore\\base\\ngscb\\wldp\\dll\\canexe"...
0x18004074c  mov     edx, 131h; void *
0x180040751  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180040756  nop
0x180040757  mov     rax, 0
0x180040761  add     rsp, 0A0h
0x180040768  pop     rbp
0x180040769  retn
```
