# WinHvCreatePartition

- ea: `0x14001f260`
- end: `0x14001f2c2`
- name: `WinHvCreatePartition`
- size: `98`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14001f2d0`

## pseudocode

```c
__int64 __fastcall WinHvCreatePartition(
        char a1,
        __int64 a2,
        int a3,
        int a4,
        __int64 a5,
        _QWORD *a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10)
{
  return WinHvCreatePartitionEx(a1, a2, a3, a4, a5, 0, a6, a7, a8, a9, a10);
}

```

## disassembly

```asm
0x14001f260  mov     r11, rsp
0x14001f263  sub     rsp, 68h
0x14001f267  mov     rax, [rsp+68h+arg_48]
0x14001f26f  mov     [r11-18h], rax
0x14001f273  mov     rax, [rsp+68h+arg_40]
0x14001f27b  mov     [r11-20h], rax
0x14001f27f  mov     rax, [rsp+68h+arg_38]
0x14001f287  mov     [r11-28h], rax
0x14001f28b  mov     rax, [rsp+68h+arg_30]
0x14001f293  mov     [r11-30h], rax
0x14001f297  mov     rax, [rsp+68h+arg_28]
0x14001f29f  mov     [r11-38h], rax
0x14001f2a3  mov     rax, [rsp+68h+arg_20]
0x14001f2ab  mov     qword ptr [r11-40h], 0
0x14001f2b3  mov     [r11-48h], rax
0x14001f2b7  call    WinHvCreatePartitionEx
0x14001f2bc  add     rsp, 68h
0x14001f2c0  retn
```
