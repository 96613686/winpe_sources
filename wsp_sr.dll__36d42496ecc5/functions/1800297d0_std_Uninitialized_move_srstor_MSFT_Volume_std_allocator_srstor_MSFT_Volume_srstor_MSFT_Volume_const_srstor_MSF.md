# std::_Uninitialized_move<srstor::MSFT_Volume *,std::allocator<srstor::MSFT_Volume>>(srstor::MSFT_Volume * const,srstor::MSFT_Volume * const,srstor::MSFT_Volume *,std::allocator<srstor::MSFT_Volume> &)

- ea: `0x1800297d0`
- end: `0x180029823`
- name: `??$_Uninitialized_move@PEAVMSFT_Volume@srstor@@V?$allocator@VMSFT_Volume@srstor@@@std@@@std@@YAPEAVMSFT_Volume@srstor@@QEAV12@0PEAV12@AEAV?$allocator@VMSFT_Volume@srstor@@@0@@Z`
- size: `83`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180029690`

## callees

- `0x18001ce54`
- `0x1800297d0`
- `0x18002982c`

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
0x1800297d0  mov     [rsp+arg_0], rbx
0x1800297d5  mov     [rsp+arg_8], rsi
0x1800297da  push    rdi
0x1800297db  sub     rsp, 20h
0x1800297df  mov     rbx, r8
0x1800297e2  mov     rsi, rdx
0x1800297e5  mov     rdi, rcx
0x1800297e8  cmp     rcx, rdx
0x1800297eb  jz      short loc_180029805
0x1800297ed  mov     r8, rdi
0x1800297f0  mov     rdx, rbx
0x1800297f3  call    ??$construct@VMSFT_Volume@srstor@@V12@@?$_Default_allocator_traits@V?$allocator@VMSFT_Volume@srstor@@@std@@@std@@SAXAEAV?$allocator@VMSFT_Volume@srstor@@@1@QEAVMSFT_Volume@srstor@@$$QEAV34@@Z; std::_Default_allocator_traits<std::allocator<srstor::MSFT_Volume>>::construct<srstor::MSFT_Volume,srstor::MSFT_Volume>(std::allocator<srstor::MSFT_Volume> &,srstor::MSFT_Volume * const,srstor::MSFT_Volume &&)
0x1800297f8  add     rbx, 40h ; '@'
0x1800297fc  add     rdi, 40h ; '@'
0x180029800  cmp     rdi, rsi
0x180029803  jnz     short loc_1800297ED
0x180029805  mov     rdx, rbx
0x180029808  mov     rcx, rbx
0x18002980b  call    ??$_Destroy_range@V?$allocator@VMSFT_Volume@srstor@@@std@@@std@@YAXPEAVMSFT_Volume@srstor@@QEAV12@AEAV?$allocator@VMSFT_Volume@srstor@@@0@@Z; std::_Destroy_range<std::allocator<srstor::MSFT_Volume>>(srstor::MSFT_Volume *,srstor::MSFT_Volume * const,std::allocator<srstor::MSFT_Volume> &)
0x180029810  mov     rsi, [rsp+28h+arg_8]
0x180029815  mov     rax, rbx
0x180029818  mov     rbx, [rsp+28h+arg_0]
0x18002981d  add     rsp, 20h
0x180029821  pop     rdi
0x180029822  retn
```
