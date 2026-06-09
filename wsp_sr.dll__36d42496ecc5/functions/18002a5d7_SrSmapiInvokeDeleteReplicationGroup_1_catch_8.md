# _SrSmapiInvokeDeleteReplicationGroup_::_1_::catch$8

- ea: `0x18002a5d7`
- end: `0x18002a605`
- name: `_SrSmapiInvokeDeleteReplicationGroup_::_1_::catch$8`
- size: `46`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800224a4`

## pseudocode

```c
__int64 __fastcall SrSmapiInvokeDeleteReplicationGroup_::_1_::catch_8(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 40) = CatchErrorFromMiClient(
                           *(const struct std::system_error **)(a2 + 96),
                           *(struct CWMIContext **)(a2 + 48));
  return 0;
}

```

## disassembly

```asm
0x18002a5d7  mov     [rsp+arg_8], rdx
0x18002a5dc  push    rbp
0x18002a5dd  sub     rsp, 20h
0x18002a5e1  mov     rbp, rdx
0x18002a5e4  mov     rdx, [rbp+30h]; struct CWMIContext *
0x18002a5e8  mov     rcx, [rbp+60h]; struct std::system_error *
0x18002a5ec  call    ?CatchErrorFromMiClient@@YA?AW4_MI_Result@@AEBVsystem_error@std@@AEAVCWMIContext@@@Z; CatchErrorFromMiClient(std::system_error const &,CWMIContext &)
0x18002a5f1  mov     [rbp+28h], eax
0x18002a5f4  mov     rax, 0
0x18002a5fe  add     rsp, 20h
0x18002a602  pop     rbp
0x18002a603  retn
```
