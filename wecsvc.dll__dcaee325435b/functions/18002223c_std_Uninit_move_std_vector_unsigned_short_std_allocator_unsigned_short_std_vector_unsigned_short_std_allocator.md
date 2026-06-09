# _std::_Uninit_move_std::vector_unsigned_short_std::allocator_unsigned_short______std::vector_unsigned_short_std::allocator_unsigned_short______std::allocator_std::vector_unsigned_short_std::allocator_unsigned_short______std::vector_unsigned_short_std::allocator_unsigned_short______::_1_::catch$0

- ea: `0x18002223c`
- end: `0x18002226c`
- name: `_std::_Uninit_move_std::vector_unsigned_short_std::allocator_unsigned_short______std::vector_unsigned_short_std::allocator_unsigned_short______std::allocator_std::vector_unsigned_short_std::allocator_unsigned_short______std::vector_unsigned_short_std::allocator_unsigned_short______::_1_::catch$0`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000195c`
- `0x180006334`
- `0x18002223c`

## pseudocode

```c
void __fastcall __noreturn std::_Uninit_move_std::vector_unsigned_short_std::allocator_unsigned_short______std::vector_unsigned_short_std::allocator_unsigned_short______std::allocator_std::vector_unsigned_short_std::allocator_unsigned_short______std::vector_unsigned_short_std::allocator_unsigned_short______::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  __int64 i; // rbx

  for ( i = *(_QWORD *)(a2 + 72); i != *(_QWORD *)(a2 + 64); i += 24 )
    std::vector<_WSMAN_OPTION>::~vector<_WSMAN_OPTION>(i);
  throw;
}

```

## disassembly

```asm
0x18002223c  mov     [rsp+arg_8], rdx
0x180022241  push    rbx
0x180022242  push    rbp
0x180022243  sub     rsp, 28h
0x180022247  mov     rbp, rdx
0x18002224a  mov     rbx, [rbp+48h]
0x18002224e  jmp     short loc_18002225C
0x180022250  mov     rcx, rbx
0x180022253  call    ??1?$vector@U_WSMAN_OPTION@@V?$allocator@U_WSMAN_OPTION@@@std@@@std@@QEAA@XZ; std::vector<_WSMAN_OPTION>::~vector<_WSMAN_OPTION>(void)
0x180022258  add     rbx, 18h
0x18002225c  cmp     rbx, [rbp+40h]
0x180022260  jnz     short loc_180022250
0x180022262  xor     edx, edx; pThrowInfo
0x180022264  xor     ecx, ecx; pExceptionObject
0x180022266  call    _CxxThrowException_0
```
