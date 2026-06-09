# std::_Uninitialized_move<srstor::MSFT_StorageNode *,std::allocator<srstor::MSFT_StorageNode>>(srstor::MSFT_StorageNode * const,srstor::MSFT_StorageNode * const,srstor::MSFT_StorageNode *,std::allocator<srstor::MSFT_StorageNode> &)

- ea: `0x180029608`
- end: `0x18002965c`
- name: `??$_Uninitialized_move@PEAVMSFT_StorageNode@srstor@@V?$allocator@VMSFT_StorageNode@srstor@@@std@@@std@@YAPEAVMSFT_StorageNode@srstor@@QEAV12@0PEAV12@AEAV?$allocator@VMSFT_StorageNode@srstor@@@0@@Z`
- size: `84`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800294c4`

## callees

- `0x18001cf70`
- `0x180029608`
- `0x180029664`

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
0x180029608  mov     [rsp+arg_0], rbx
0x18002960d  mov     [rsp+arg_8], rsi
0x180029612  push    rdi
0x180029613  sub     rsp, 20h
0x180029617  mov     rbx, r8
0x18002961a  mov     rsi, rdx
0x18002961d  mov     rdi, rcx
0x180029620  cmp     rcx, rdx
0x180029623  jz      short loc_18002963D
0x180029625  mov     r8, rdi
0x180029628  mov     rdx, rbx
0x18002962b  call    ??$construct@VMSFT_StorageNode@srstor@@V12@@?$_Default_allocator_traits@V?$allocator@VMSFT_StorageNode@srstor@@@std@@@std@@SAXAEAV?$allocator@VMSFT_StorageNode@srstor@@@1@QEAVMSFT_StorageNode@srstor@@$$QEAV34@@Z; std::_Default_allocator_traits<std::allocator<srstor::MSFT_StorageNode>>::construct<srstor::MSFT_StorageNode,srstor::MSFT_StorageNode>(std::allocator<srstor::MSFT_StorageNode> &,srstor::MSFT_StorageNode * const,srstor::MSFT_StorageNode &&)
0x180029630  add     rbx, 40h ; '@'
0x180029634  add     rdi, 40h ; '@'
0x180029638  cmp     rdi, rsi
0x18002963b  jnz     short loc_180029625
0x18002963d  mov     rdx, rbx
0x180029640  mov     rcx, rbx
0x180029643  call    ??$_Destroy_range@V?$allocator@VMSFT_Volume@srstor@@@std@@@std@@YAXPEAVMSFT_Volume@srstor@@QEAV12@AEAV?$allocator@VMSFT_Volume@srstor@@@0@@Z; std::_Destroy_range<std::allocator<srstor::MSFT_Volume>>(srstor::MSFT_Volume *,srstor::MSFT_Volume * const,std::allocator<srstor::MSFT_Volume> &)
0x180029648  mov     rsi, [rsp+28h+arg_8]
0x18002964d  mov     rax, rbx
0x180029650  mov     rbx, [rsp+28h+arg_0]
0x180029655  add     rsp, 20h
0x180029659  pop     rdi
0x18002965a  retn
```
