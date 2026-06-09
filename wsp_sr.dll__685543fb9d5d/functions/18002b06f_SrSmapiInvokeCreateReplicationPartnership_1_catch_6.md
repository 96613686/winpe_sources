# _SrSmapiInvokeCreateReplicationPartnership_::_1_::catch$6

- ea: `0x18002b06f`
- end: `0x18002b0ac`
- name: `_SrSmapiInvokeCreateReplicationPartnership_::_1_::catch$6`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180022660`

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
0x18002b06f  mov     [rsp+arg_8], rdx
0x18002b074  push    rbp
0x18002b075  sub     rsp, 0B0h
0x18002b07c  mov     rbp, rdx
0x18002b07f  mov     rdx, [rbp+0C0h]; struct CWMIContext *
0x18002b086  mov     rcx, [rbp+138h]; struct std::system_error *
0x18002b08d  call    ?CatchErrorFromMiClient@@YA?AW4_MI_Result@@AEBVsystem_error@std@@AEAVCWMIContext@@@Z; CatchErrorFromMiClient(std::system_error const &,CWMIContext &)
0x18002b092  mov     [rbp+0B0h], eax
0x18002b098  mov     rax, 0
0x18002b0a2  add     rsp, 0B0h
0x18002b0a9  pop     rbp
0x18002b0aa  retn
```
