# _SrSmapiInvokeCreateReplicationPartnership_::_1_::catch$6

- ea: `0x18002aba1`
- end: `0x18002abde`
- name: `_SrSmapiInvokeCreateReplicationPartnership_::_1_::catch$6`
- size: `61`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800224a4`

## pseudocode

```c
__int64 __fastcall SrSmapiInvokeCreateReplicationPartnership_::_1_::catch_6(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 176) = CatchErrorFromMiClient(
                            *(const struct std::system_error **)(a2 + 312),
                            *(struct CWMIContext **)(a2 + 192));
  return 0;
}

```

## disassembly

```asm
0x18002aba1  mov     [rsp+arg_8], rdx
0x18002aba6  push    rbp
0x18002aba7  sub     rsp, 0B0h
0x18002abae  mov     rbp, rdx
0x18002abb1  mov     rdx, [rbp+0C0h]; struct CWMIContext *
0x18002abb8  mov     rcx, [rbp+138h]; struct std::system_error *
0x18002abbf  call    ?CatchErrorFromMiClient@@YA?AW4_MI_Result@@AEBVsystem_error@std@@AEAVCWMIContext@@@Z; CatchErrorFromMiClient(std::system_error const &,CWMIContext &)
0x18002abc4  mov     [rbp+0B0h], eax
0x18002abca  mov     rax, 0
0x18002abd4  add     rsp, 0B0h
0x18002abdb  pop     rbp
0x18002abdc  retn
```
