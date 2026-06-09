# WinHvDeleteCpuGroup

- ea: `0x140021030`
- end: `0x140021064`
- name: `WinHvDeleteCpuGroup`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140002ce8`
- `0x140004564`

## pseudocode

```c
__int64 WinHvDeleteCpuGroup()
{
  _QWORD v1[3]; // [rsp+20h] [rbp-18h] BYREF

  v1[1] = 0;
  v1[0] = WinHvpInitializeFastHypercall(v1);
  return WinHvpFastHypercall(182, v1);
}

```

## disassembly

```asm
0x140021030  sub     rsp, 38h
0x140021034  mov     rax, rcx
0x140021037  mov     [rsp+38h+var_10], 0
0x140021040  lea     rcx, [rsp+38h+var_18]
0x140021045  call    WinHvpInitializeFastHypercall
0x14002104a  lea     rdx, [rsp+38h+var_18]
0x14002104f  mov     [rsp+38h+var_18], rax
0x140021054  mov     ecx, 0B6h
0x140021059  call    WinHvpFastHypercall
0x14002105e  add     rsp, 38h
0x140021062  retn
```
