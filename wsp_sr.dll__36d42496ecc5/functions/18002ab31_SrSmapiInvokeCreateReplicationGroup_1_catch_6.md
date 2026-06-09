# _SrSmapiInvokeCreateReplicationGroup_::_1_::catch$6

- ea: `0x18002ab31`
- end: `0x18002ab65`
- name: `_SrSmapiInvokeCreateReplicationGroup_::_1_::catch$6`
- size: `52`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800224a4`

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
0x18002ab31  mov     [rsp+arg_8], rdx
0x18002ab36  push    rbp
0x18002ab37  sub     rsp, 70h
0x18002ab3b  mov     rbp, rdx
0x18002ab3e  mov     rdx, [rbp+80h]; struct CWMIContext *
0x18002ab45  mov     rcx, [rbp+0D8h]; struct std::system_error *
0x18002ab4c  call    ?CatchErrorFromMiClient@@YA?AW4_MI_Result@@AEBVsystem_error@std@@AEAVCWMIContext@@@Z; CatchErrorFromMiClient(std::system_error const &,CWMIContext &)
0x18002ab51  mov     [rbp+70h], eax
0x18002ab54  mov     rax, 0
0x18002ab5e  add     rsp, 70h
0x18002ab62  pop     rbp
0x18002ab63  retn
```
