# WPP_SF_D

- ea: `0x1800090dc`
- end: `0x180009113`
- name: `WPP_SF_D`
- size: `55`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, __int64, int)`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180008b48`
- `0x180008cac`
- `0x180008e4c`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180009108`
- `ntdll!EtwTraceMessage` at `0x180009108`

## pseudocode

```c
__int64 __fastcall WPP_SF_D(__int64 a1, unsigned __int16 a2, __int64 a3, int a4)
{
  int v5; // [rsp+68h] [rbp+20h] BYREF

  v5 = a4;
  return EtwTraceMessage(a1, 43, a3, a2, &v5, 4, 0);
}

```

## disassembly

```asm
0x1800090dc  mov     r11, rsp
0x1800090df  mov     [r11+20h], r9d
0x1800090e3  sub     rsp, 48h
0x1800090e7  mov     qword ptr [r11-18h], 0
0x1800090ef  lea     rax, [r11+20h]
0x1800090f3  movzx   r9d, dx
0x1800090f7  mov     edx, 2Bh ; '+'
0x1800090fc  mov     qword ptr [r11-20h], 4
0x180009104  mov     [r11-28h], rax
0x180009108  call    cs:__imp_EtwTraceMessage
0x18000910e  add     rsp, 48h
0x180009112  retn
```
