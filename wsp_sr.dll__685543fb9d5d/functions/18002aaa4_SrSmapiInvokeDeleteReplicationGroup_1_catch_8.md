# _SrSmapiInvokeDeleteReplicationGroup_::_1_::catch$8

- ea: `0x18002aaa4`
- end: `0x18002aad2`
- name: `_SrSmapiInvokeDeleteReplicationGroup_::_1_::catch$8`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180022660`

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
0x18002aaa4  mov     [rsp+arg_8], rdx
0x18002aaa9  push    rbp
0x18002aaaa  sub     rsp, 20h
0x18002aaae  mov     rbp, rdx
0x18002aab1  mov     rdx, [rbp+30h]; struct CWMIContext *
0x18002aab5  mov     rcx, [rbp+60h]; struct std::system_error *
0x18002aab9  call    ?CatchErrorFromMiClient@@YA?AW4_MI_Result@@AEBVsystem_error@std@@AEAVCWMIContext@@@Z; CatchErrorFromMiClient(std::system_error const &,CWMIContext &)
0x18002aabe  mov     [rbp+28h], eax
0x18002aac1  mov     rax, 0
0x18002aacb  add     rsp, 20h
0x18002aacf  pop     rbp
0x18002aad0  retn
```
