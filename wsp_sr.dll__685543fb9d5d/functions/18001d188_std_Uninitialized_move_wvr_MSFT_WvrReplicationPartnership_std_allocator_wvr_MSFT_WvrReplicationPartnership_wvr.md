# std::_Uninitialized_move<wvr::MSFT_WvrReplicationPartnership *,std::allocator<wvr::MSFT_WvrReplicationPartnership>>(wvr::MSFT_WvrReplicationPartnership * const,wvr::MSFT_WvrReplicationPartnership * const,wvr::MSFT_WvrReplicationPartnership *,std::allocator<wvr::MSFT_WvrReplicationPartnership> &)

- ea: `0x18001d188`
- end: `0x18001d1dc`
- name: `??$_Uninitialized_move@PEAVMSFT_WvrReplicationPartnership@wvr@@V?$allocator@VMSFT_WvrReplicationPartnership@wvr@@@std@@@std@@YAPEAVMSFT_WvrReplicationPartnership@wvr@@QEAV12@0PEAV12@AEAV?$allocator@VMSFT_WvrReplicationPartnership@wvr@@@0@@Z`
- size: `84`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001cfe8`

## callees

- `0x18001cf70`
- `0x18001d188`
- `0x1800211e8`

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
0x18001d188  mov     [rsp+arg_0], rbx
0x18001d18d  mov     [rsp+arg_8], rsi
0x18001d192  push    rdi
0x18001d193  sub     rsp, 20h
0x18001d197  mov     rbx, r8
0x18001d19a  mov     rsi, rdx
0x18001d19d  mov     rdi, rcx
0x18001d1a0  cmp     rcx, rdx
0x18001d1a3  jz      short loc_18001D1BD
0x18001d1a5  mov     rdx, rdi
0x18001d1a8  mov     rcx, rbx
0x18001d1ab  call    ??0MSFT_WvrReplicationPartnership@wvr@@QEAA@$$QEAV01@@Z
0x18001d1b0  add     rbx, 40h ; '@'
0x18001d1b4  add     rdi, 40h ; '@'
0x18001d1b8  cmp     rdi, rsi
0x18001d1bb  jnz     short loc_18001D1A5
0x18001d1bd  mov     rdx, rbx
0x18001d1c0  mov     rcx, rbx
0x18001d1c3  call    ??$_Destroy_range@V?$allocator@VMSFT_Volume@srstor@@@std@@@std@@YAXPEAVMSFT_Volume@srstor@@QEAV12@AEAV?$allocator@VMSFT_Volume@srstor@@@0@@Z
0x18001d1c8  mov     rsi, [rsp+28h+arg_8]
0x18001d1cd  mov     rax, rbx
0x18001d1d0  mov     rbx, [rsp+28h+arg_0]
0x18001d1d5  add     rsp, 20h
0x18001d1d9  pop     rdi
0x18001d1da  retn
```
