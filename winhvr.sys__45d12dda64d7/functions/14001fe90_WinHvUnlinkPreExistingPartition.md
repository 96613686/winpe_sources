# WinHvUnlinkPreExistingPartition

- ea: `0x14001fe90`
- end: `0x14001fea1`
- name: `WinHvUnlinkPreExistingPartition`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1400204a4`

## pseudocode

```c
__int64 __fastcall WinHvUnlinkPreExistingPartition(unsigned __int64 a1)
{
  return WinHvpDeleteWinHvPartition(a1, 1);
}

```

## disassembly

```asm
0x14001fe90  sub     rsp, 28h
0x14001fe94  mov     dl, 1
0x14001fe96  call    WinHvpDeleteWinHvPartition
0x14001fe9b  add     rsp, 28h
0x14001fe9f  retn
```
