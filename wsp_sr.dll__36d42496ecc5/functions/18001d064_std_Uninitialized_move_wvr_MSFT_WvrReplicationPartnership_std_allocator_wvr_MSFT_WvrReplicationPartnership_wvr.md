# std::_Uninitialized_move<wvr::MSFT_WvrReplicationPartnership *,std::allocator<wvr::MSFT_WvrReplicationPartnership>>(wvr::MSFT_WvrReplicationPartnership * const,wvr::MSFT_WvrReplicationPartnership * const,wvr::MSFT_WvrReplicationPartnership *,std::allocator<wvr::MSFT_WvrReplicationPartnership> &)

- ea: `0x18001d064`
- end: `0x18001d0b7`
- name: `??$_Uninitialized_move@PEAVMSFT_WvrReplicationPartnership@wvr@@V?$allocator@VMSFT_WvrReplicationPartnership@wvr@@@std@@@std@@YAPEAVMSFT_WvrReplicationPartnership@wvr@@QEAV12@0PEAV12@AEAV?$allocator@VMSFT_WvrReplicationPartnership@wvr@@@0@@Z`
- size: `83`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001cecc`

## callees

- `0x18001ce54`
- `0x18001d064`
- `0x18002105c`

## pseudocode

```c
__int64 __fastcall std::_Uninitialized_move<wvr::MSFT_WvrReplicationPartnership *>(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 i; // rdi

  for ( i = a1; i != a2; i += 64 )
  {
    wvr::MSFT_WvrReplicationPartnership::MSFT_WvrReplicationPartnership(a3, i);
    a3 += 64;
  }
  std::_Destroy_range<std::allocator<srstor::MSFT_Volume>>(a3, a3);
  return a3;
}

```

## disassembly

```asm
0x18001d064  mov     [rsp+arg_0], rbx
0x18001d069  mov     [rsp+arg_8], rsi
0x18001d06e  push    rdi
0x18001d06f  sub     rsp, 20h
0x18001d073  mov     rbx, r8
0x18001d076  mov     rsi, rdx
0x18001d079  mov     rdi, rcx
0x18001d07c  cmp     rcx, rdx
0x18001d07f  jz      short loc_18001D099
0x18001d081  mov     rdx, rdi
0x18001d084  mov     rcx, rbx
0x18001d087  call    ??0MSFT_WvrReplicationPartnership@wvr@@QEAA@$$QEAV01@@Z
0x18001d08c  add     rbx, 40h ; '@'
0x18001d090  add     rdi, 40h ; '@'
0x18001d094  cmp     rdi, rsi
0x18001d097  jnz     short loc_18001D081
0x18001d099  mov     rdx, rbx
0x18001d09c  mov     rcx, rbx
0x18001d09f  call    ??$_Destroy_range@V?$allocator@VMSFT_Volume@srstor@@@std@@@std@@YAXPEAVMSFT_Volume@srstor@@QEAV12@AEAV?$allocator@VMSFT_Volume@srstor@@@0@@Z
0x18001d0a4  mov     rsi, [rsp+28h+arg_8]
0x18001d0a9  mov     rax, rbx
0x18001d0ac  mov     rbx, [rsp+28h+arg_0]
0x18001d0b1  add     rsp, 20h
0x18001d0b5  pop     rdi
0x18001d0b6  retn
```
