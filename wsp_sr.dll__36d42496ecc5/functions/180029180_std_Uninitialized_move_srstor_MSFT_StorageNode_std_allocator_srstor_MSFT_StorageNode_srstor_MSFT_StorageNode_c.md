# std::_Uninitialized_move<srstor::MSFT_StorageNode *,std::allocator<srstor::MSFT_StorageNode>>(srstor::MSFT_StorageNode * const,srstor::MSFT_StorageNode * const,srstor::MSFT_StorageNode *,std::allocator<srstor::MSFT_StorageNode> &)

- ea: `0x180029180`
- end: `0x1800291d3`
- name: `??$_Uninitialized_move@PEAVMSFT_StorageNode@srstor@@V?$allocator@VMSFT_StorageNode@srstor@@@std@@@std@@YAPEAVMSFT_StorageNode@srstor@@QEAV12@0PEAV12@AEAV?$allocator@VMSFT_StorageNode@srstor@@@0@@Z`
- size: `83`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180029040`

## callees

- `0x18001ce54`
- `0x180029180`
- `0x1800291dc`

## pseudocode

```c
__int64 __fastcall std::_Uninitialized_move<srstor::MSFT_StorageNode *>(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 i; // rdi

  for ( i = a1; i != a2; i += 64 )
  {
    std::_Default_allocator_traits<std::allocator<srstor::MSFT_StorageNode>>::construct<srstor::MSFT_StorageNode,srstor::MSFT_StorageNode>(
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
0x180029180  mov     [rsp+arg_0], rbx
0x180029185  mov     [rsp+arg_8], rsi
0x18002918a  push    rdi
0x18002918b  sub     rsp, 20h
0x18002918f  mov     rbx, r8
0x180029192  mov     rsi, rdx
0x180029195  mov     rdi, rcx
0x180029198  cmp     rcx, rdx
0x18002919b  jz      short loc_1800291B5
0x18002919d  mov     r8, rdi
0x1800291a0  mov     rdx, rbx
0x1800291a3  call    ??$construct@VMSFT_StorageNode@srstor@@V12@@?$_Default_allocator_traits@V?$allocator@VMSFT_StorageNode@srstor@@@std@@@std@@SAXAEAV?$allocator@VMSFT_StorageNode@srstor@@@1@QEAVMSFT_StorageNode@srstor@@$$QEAV34@@Z; std::_Default_allocator_traits<std::allocator<srstor::MSFT_StorageNode>>::construct<srstor::MSFT_StorageNode,srstor::MSFT_StorageNode>(std::allocator<srstor::MSFT_StorageNode> &,srstor::MSFT_StorageNode * const,srstor::MSFT_StorageNode &&)
0x1800291a8  add     rbx, 40h ; '@'
0x1800291ac  add     rdi, 40h ; '@'
0x1800291b0  cmp     rdi, rsi
0x1800291b3  jnz     short loc_18002919D
0x1800291b5  mov     rdx, rbx
0x1800291b8  mov     rcx, rbx
0x1800291bb  call    ??$_Destroy_range@V?$allocator@VMSFT_Volume@srstor@@@std@@@std@@YAXPEAVMSFT_Volume@srstor@@QEAV12@AEAV?$allocator@VMSFT_Volume@srstor@@@0@@Z; std::_Destroy_range<std::allocator<srstor::MSFT_Volume>>(srstor::MSFT_Volume *,srstor::MSFT_Volume * const,std::allocator<srstor::MSFT_Volume> &)
0x1800291c0  mov     rsi, [rsp+28h+arg_8]
0x1800291c5  mov     rax, rbx
0x1800291c8  mov     rbx, [rsp+28h+arg_0]
0x1800291cd  add     rsp, 20h
0x1800291d1  pop     rdi
0x1800291d2  retn
```
