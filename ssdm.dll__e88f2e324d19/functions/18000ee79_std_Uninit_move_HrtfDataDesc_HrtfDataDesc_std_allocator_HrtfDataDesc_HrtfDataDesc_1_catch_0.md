# _std::_Uninit_move_HrtfDataDesc___HrtfDataDesc___std::allocator_HrtfDataDesc__HrtfDataDesc__::_1_::catch$0

- ea: `0x18000ee79`
- end: `0x18000eea9`
- name: `_std::_Uninit_move_HrtfDataDesc___HrtfDataDesc___std::allocator_HrtfDataDesc__HrtfDataDesc__::_1_::catch$0`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180002ebc`
- `0x1800041a0`
- `0x18000ee79`

## pseudocode

```c
void __fastcall __noreturn std::_Uninit_move_HrtfDataDesc___HrtfDataDesc___std::allocator_HrtfDataDesc__HrtfDataDesc__::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  __int64 i; // rbx

  for ( i = *(_QWORD *)(a2 + 72); i != *(_QWORD *)(a2 + 64); i += 56 )
    std::_Wrap_alloc<std::allocator<HrtfDataDesc>>::destroy<HrtfDataDesc>(a1, i);
  throw;
}

```

## disassembly

```asm
0x18000ee79  mov     [rsp+arg_8], rdx
0x18000ee7e  push    rbx
0x18000ee7f  push    rbp
0x18000ee80  sub     rsp, 28h
0x18000ee84  mov     rbp, rdx
0x18000ee87  mov     rbx, [rbp+48h]
0x18000ee8b  jmp     short loc_18000EE99
0x18000ee8d  mov     rdx, rbx
0x18000ee90  call    ??$destroy@UHrtfDataDesc@@@?$_Wrap_alloc@V?$allocator@UHrtfDataDesc@@@std@@@std@@QEAAXPEAUHrtfDataDesc@@@Z; std::_Wrap_alloc<std::allocator<HrtfDataDesc>>::destroy<HrtfDataDesc>(HrtfDataDesc *)
0x18000ee95  add     rbx, 38h ; '8'
0x18000ee99  cmp     rbx, [rbp+40h]
0x18000ee9d  jnz     short loc_18000EE8D
0x18000ee9f  xor     edx, edx; pThrowInfo
0x18000eea1  xor     ecx, ecx; pExceptionObject
0x18000eea3  call    _CxxThrowException_0
```
