# WinHvDeletePartition

- ea: `0x14001f890`
- end: `0x14001f8a6`
- name: `WinHvDeletePartition`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400202cc`

## pseudocode

```c
__int64 __fastcall WinHvDeletePartition(unsigned __int64 a1)
{
  return WinHvpDeletePartition(a1, (__int64 (__fastcall *)(unsigned __int64))WinHvWithdrawAllMemory);
}

```

## disassembly

```asm
0x14001f890  sub     rsp, 28h
0x14001f894  lea     rdx, WinHvWithdrawAllMemory
0x14001f89b  call    WinHvpDeletePartition
0x14001f8a0  add     rsp, 28h
0x14001f8a4  retn
```
