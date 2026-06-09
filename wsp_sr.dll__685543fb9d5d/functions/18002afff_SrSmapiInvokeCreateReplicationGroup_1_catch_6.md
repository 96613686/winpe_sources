# _SrSmapiInvokeCreateReplicationGroup_::_1_::catch$6

- ea: `0x18002afff`
- end: `0x18002b033`
- name: `_SrSmapiInvokeCreateReplicationGroup_::_1_::catch$6`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180022660`

## pseudocode

```c
__int64 __fastcall SrSmapiInvokeCreateReplicationGroup_::_1_::catch_6(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 112) = CatchErrorFromMiClient(
                            *(const struct std::system_error **)(a2 + 216),
                            *(struct CWMIContext **)(a2 + 128));
  return 0;
}

```

## disassembly

```asm
0x18002afff  mov     [rsp+arg_8], rdx
0x18002b004  push    rbp
0x18002b005  sub     rsp, 70h
0x18002b009  mov     rbp, rdx
0x18002b00c  mov     rdx, [rbp+80h]; struct CWMIContext *
0x18002b013  mov     rcx, [rbp+0D8h]; struct std::system_error *
0x18002b01a  call    ?CatchErrorFromMiClient@@YA?AW4_MI_Result@@AEBVsystem_error@std@@AEAVCWMIContext@@@Z; CatchErrorFromMiClient(std::system_error const &,CWMIContext &)
0x18002b01f  mov     [rbp+70h], eax
0x18002b022  mov     rax, 0
0x18002b02c  add     rsp, 70h
0x18002b030  pop     rbp
0x18002b031  retn
```
