# _SrSmapiInvokeRemoveReplicationRelationship_::_1_::catch$6

- ea: `0x18002abe4`
- end: `0x18002ac12`
- name: `_SrSmapiInvokeRemoveReplicationRelationship_::_1_::catch$6`
- size: `46`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800224a4`

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
0x18002abe4  mov     [rsp+arg_8], rdx
0x18002abe9  push    rbp
0x18002abea  sub     rsp, 30h
0x18002abee  mov     rbp, rdx
0x18002abf1  mov     rdx, [rbp+40h]; struct CWMIContext *
0x18002abf5  mov     rcx, [rbp+70h]; struct std::system_error *
0x18002abf9  call    ?CatchErrorFromMiClient@@YA?AW4_MI_Result@@AEBVsystem_error@std@@AEAVCWMIContext@@@Z; CatchErrorFromMiClient(std::system_error const &,CWMIContext &)
0x18002abfe  mov     [rbp+38h], eax
0x18002ac01  mov     rax, 0
0x18002ac0b  add     rsp, 30h
0x18002ac0f  pop     rbp
0x18002ac10  retn
```
