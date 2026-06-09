# WPP_SF_q

- ea: `0x180011dac`
- end: `0x180011de3`
- name: `WPP_SF_q`
- size: `55`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180017b20`
- `0x180017d30`
- `0x18001ce10`
- `0x18001dc78`
- `0x18001e8c8`
- `0x18001ebc0`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180011dd8`
- `ntdll!EtwTraceMessage` at `0x180011dd8`

## pseudocode

```c
__int64 WPP_SF_q(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
{
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  return EtwTraceMessage(a1, 43, a3, a2, (__int64 *)va, 8, 0);
}

```

## disassembly

```asm
0x180011dac  mov     r11, rsp
0x180011daf  mov     [r11+20h], r9
0x180011db3  sub     rsp, 48h
0x180011db7  mov     qword ptr [r11-18h], 0
0x180011dbf  lea     rax, [r11+20h]
0x180011dc3  movzx   r9d, dx
0x180011dc7  mov     edx, 2Bh ; '+'
0x180011dcc  mov     qword ptr [r11-20h], 8
0x180011dd4  mov     [r11-28h], rax
0x180011dd8  call    cs:__imp_EtwTraceMessage
0x180011dde  add     rsp, 48h
0x180011de2  retn
```
