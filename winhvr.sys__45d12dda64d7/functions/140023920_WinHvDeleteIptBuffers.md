# WinHvDeleteIptBuffers

- ea: `0x140023920`
- end: `0x14002396a`
- name: `WinHvDeleteIptBuffers`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140002ce8`
- `0x140004564`
- `0x140022af0`
- `0x140023920`

## pseudocode

```c
__int64 WinHvDeleteIptBuffers()
{
  int v0; // ebx
  _QWORD v2[3]; // [rsp+20h] [rbp-18h] BYREF

  v2[1] = 0;
  v2[0] = WinHvpInitializeFastHypercall(v2);
  v0 = WinHvpFastHypercall(232, v2);
  if ( v0 >= 0 )
    WinHvWithdrawAllMemoryWithCount(-1, 0);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x140023920  push    rbx
0x140023922  sub     rsp, 30h
0x140023926  mov     rax, rcx
0x140023929  mov     [rsp+38h+var_10], 0
0x140023932  lea     rcx, [rsp+38h+var_18]
0x140023937  call    WinHvpInitializeFastHypercall
0x14002393c  lea     rdx, [rsp+38h+var_18]
0x140023941  mov     [rsp+38h+var_18], rax
0x140023946  mov     ecx, 0E8h
0x14002394b  call    WinHvpFastHypercall
0x140023950  mov     ebx, eax
0x140023952  test    eax, eax
0x140023954  js      short loc_140023961
0x140023956  xor     edx, edx
0x140023958  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14002395c  call    WinHvWithdrawAllMemoryWithCount
0x140023961  mov     eax, ebx
0x140023963  add     rsp, 30h
0x140023967  pop     rbx
0x140023968  retn
```
