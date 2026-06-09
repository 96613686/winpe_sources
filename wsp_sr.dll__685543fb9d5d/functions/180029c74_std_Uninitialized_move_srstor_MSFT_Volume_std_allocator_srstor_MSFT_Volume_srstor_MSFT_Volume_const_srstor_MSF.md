# std::_Uninitialized_move<srstor::MSFT_Volume *,std::allocator<srstor::MSFT_Volume>>(srstor::MSFT_Volume * const,srstor::MSFT_Volume * const,srstor::MSFT_Volume *,std::allocator<srstor::MSFT_Volume> &)

- ea: `0x180029c74`
- end: `0x180029cc8`
- name: `??$_Uninitialized_move@PEAVMSFT_Volume@srstor@@V?$allocator@VMSFT_Volume@srstor@@@std@@@std@@YAPEAVMSFT_Volume@srstor@@QEAV12@0PEAV12@AEAV?$allocator@VMSFT_Volume@srstor@@@0@@Z`
- size: `84`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180029b30`

## callees

- `0x18001cf70`
- `0x180029c74`
- `0x180029cd0`

## pseudocode

```c
__int64 __fastcall std::_Uninitialized_move<srstor::MSFT_Volume *>(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 i; // rdi

  for ( i = a1; i != a2; i += 64 )
  {
    std::_Default_allocator_traits<std::allocator<srstor::MSFT_Volume>>::construct<srstor::MSFT_Volume,srstor::MSFT_Volume>(
      a1,
      a3,
      i);
    a3 += 64;
  }
  std::_Destroy_range<std::allocator<srstor::MSFT_Volume>>(a3, a3);
  return a3;
}

```

## disassembly

```asm
0x180029c74  mov     [rsp+arg_0], rbx
0x180029c79  mov     [rsp+arg_8], rsi
0x180029c7e  push    rdi
0x180029c7f  sub     rsp, 20h
0x180029c83  mov     rbx, r8
0x180029c86  mov     rsi, rdx
0x180029c89  mov     rdi, rcx
0x180029c8c  cmp     rcx, rdx
0x180029c8f  jz      short loc_180029CA9
0x180029c91  mov     r8, rdi
0x180029c94  mov     rdx, rbx
0x180029c97  call    ??$construct@VMSFT_Volume@srstor@@V12@@?$_Default_allocator_traits@V?$allocator@VMSFT_Volume@srstor@@@std@@@std@@SAXAEAV?$allocator@VMSFT_Volume@srstor@@@1@QEAVMSFT_Volume@srstor@@$$QEAV34@@Z; std::_Default_allocator_traits<std::allocator<srstor::MSFT_Volume>>::construct<srstor::MSFT_Volume,srstor::MSFT_Volume>(std::allocator<srstor::MSFT_Volume> &,srstor::MSFT_Volume * const,srstor::MSFT_Volume &&)
0x180029c9c  add     rbx, 40h ; '@'
0x180029ca0  add     rdi, 40h ; '@'
0x180029ca4  cmp     rdi, rsi
0x180029ca7  jnz     short loc_180029C91
0x180029ca9  mov     rdx, rbx
0x180029cac  mov     rcx, rbx
0x180029caf  call    ??$_Destroy_range@V?$allocator@VMSFT_Volume@srstor@@@std@@@std@@YAXPEAVMSFT_Volume@srstor@@QEAV12@AEAV?$allocator@VMSFT_Volume@srstor@@@0@@Z; std::_Destroy_range<std::allocator<srstor::MSFT_Volume>>(srstor::MSFT_Volume *,srstor::MSFT_Volume * const,std::allocator<srstor::MSFT_Volume> &)
0x180029cb4  mov     rsi, [rsp+28h+arg_8]
0x180029cb9  mov     rax, rbx
0x180029cbc  mov     rbx, [rsp+28h+arg_0]
0x180029cc1  add     rsp, 20h
0x180029cc5  pop     rdi
0x180029cc6  retn
```
