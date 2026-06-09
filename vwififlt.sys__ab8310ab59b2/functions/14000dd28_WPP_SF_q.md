# WPP_SF_q

- ea: `0x14000dd28`
- end: `0x14000dd66`
- name: `WPP_SF_q`
- size: `62`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140003fe8`
- `0x140008e70`
- `0x140009300`
- `0x14000a260`

## callees

- `0x14000f150`

## pseudocode

```c
__int64 WPP_SF_q(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
{
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, __int64 *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           (__int64 *)va,
           8,
           0);
}

```

## disassembly

```asm
0x14000dd28  mov     r11, rsp
0x14000dd2b  mov     [r11+20h], r9
0x14000dd2f  sub     rsp, 48h
0x14000dd33  mov     rax, cs:pfnWppTraceMessage
0x14000dd3a  lea     r9, [r11+20h]
0x14000dd3e  mov     qword ptr [r11-18h], 0
0x14000dd46  mov     qword ptr [r11-20h], 8
0x14000dd4e  mov     [r11-28h], r9
0x14000dd52  movzx   r9d, dx
0x14000dd56  mov     edx, 2Bh ; '+'
0x14000dd5b  call    _guard_dispatch_icall
0x14000dd60  add     rsp, 48h
0x14000dd64  retn
```
