# WinHvFlushCache

- ea: `0x140004d60`
- end: `0x140004d8b`
- name: `WinHvFlushCache`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140002ce8`

## pseudocode

```c
__int64 WinHvFlushCache()
{
  _QWORD v1[3]; // [rsp+20h] [rbp-18h] BYREF

  v1[0] = 0;
  v1[1] = 0;
  return WinHvpFastHypercall(29, v1);
}

```

## disassembly

```asm
0x140004d60  sub     rsp, 38h
0x140004d64  lea     rdx, [rsp+38h+var_18]
0x140004d69  mov     [rsp+38h+var_18], 0
0x140004d72  mov     ecx, 1Dh
0x140004d77  mov     [rsp+38h+var_10], 0
0x140004d80  call    WinHvpFastHypercall
0x140004d85  add     rsp, 38h
0x140004d89  retn
```
