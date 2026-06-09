# WinHvpDeleteHvPartition

- ea: `0x1400077f8`
- end: `0x14000781f`
- name: `WinHvpDeleteHvPartition`
- size: `39`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14001f2d0`
- `0x1400202cc`

## callees

- `0x140002ce8`

## pseudocode

```c
__int64 __fastcall WinHvpDeleteHvPartition(__int64 a1)
{
  _QWORD v2[3]; // [rsp+20h] [rbp-18h] BYREF

  v2[0] = a1;
  v2[1] = 0;
  return WinHvpFastHypercall(67, v2);
}

```

## disassembly

```asm
0x1400077f8  sub     rsp, 38h
0x1400077fc  mov     [rsp+38h+var_18], rcx
0x140007801  lea     rdx, [rsp+38h+var_18]
0x140007806  mov     ecx, 43h ; 'C'
0x14000780b  mov     [rsp+38h+var_10], 0
0x140007814  call    WinHvpFastHypercall
0x140007819  add     rsp, 38h
0x14000781d  retn
```
