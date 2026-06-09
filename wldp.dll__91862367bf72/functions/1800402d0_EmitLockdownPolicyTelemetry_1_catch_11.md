# _EmitLockdownPolicyTelemetry_::_1_::catch$11

- ea: `0x1800402d0`
- end: `0x18004030d`
- name: `_EmitLockdownPolicyTelemetry_::_1_::catch$11`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x1800279e4`

## string_xrefs

- `0x1800402e7`: `onecore\base\ngscb\wldp\dll\wldp.cpp`

## pseudocode

```c
__int64 __fastcall EmitLockdownPolicyTelemetry_::_1_::catch_11(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 664),
    (void *)0x263,
    (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\wldp.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x1800402d0  mov     [rsp+arg_8], rdx
0x1800402d5  push    rbp
0x1800402d6  sub     rsp, 0A0h
0x1800402dd  mov     rbp, rdx
0x1800402e0  mov     rcx, [rbp+298h]; this
0x1800402e7  lea     r8, aOnecoreBaseNgs_5; "onecore\\base\\ngscb\\wldp\\dll\\wldp.c"...
0x1800402ee  mov     edx, 263h; void *
0x1800402f3  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x1800402f8  nop
0x1800402f9  mov     rax, 0
0x180040303  add     rsp, 0A0h
0x18004030a  pop     rbp
0x18004030b  retn
```
