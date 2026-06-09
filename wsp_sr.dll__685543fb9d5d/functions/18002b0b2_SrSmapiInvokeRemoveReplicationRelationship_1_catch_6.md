# _SrSmapiInvokeRemoveReplicationRelationship_::_1_::catch$6

- ea: `0x18002b0b2`
- end: `0x18002b0e0`
- name: `_SrSmapiInvokeRemoveReplicationRelationship_::_1_::catch$6`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180022660`

## pseudocode

```c
__int64 __fastcall SrSmapiInvokeRemoveReplicationRelationship_::_1_::catch_6(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 56) = CatchErrorFromMiClient(
                           *(const struct std::system_error **)(a2 + 112),
                           *(struct CWMIContext **)(a2 + 64));
  return 0;
}

```

## disassembly

```asm
0x18002b0b2  mov     [rsp+arg_8], rdx
0x18002b0b7  push    rbp
0x18002b0b8  sub     rsp, 30h
0x18002b0bc  mov     rbp, rdx
0x18002b0bf  mov     rdx, [rbp+40h]; struct CWMIContext *
0x18002b0c3  mov     rcx, [rbp+70h]; struct std::system_error *
0x18002b0c7  call    ?CatchErrorFromMiClient@@YA?AW4_MI_Result@@AEBVsystem_error@std@@AEAVCWMIContext@@@Z; CatchErrorFromMiClient(std::system_error const &,CWMIContext &)
0x18002b0cc  mov     [rbp+38h], eax
0x18002b0cf  mov     rax, 0
0x18002b0d9  add     rsp, 30h
0x18002b0dd  pop     rbp
0x18002b0de  retn
```
