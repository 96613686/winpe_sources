# WPP_SF_q

- ea: `0x1400055cc`
- end: `0x14000560a`
- name: `WPP_SF_q`
- size: `62`
- prototype: ``
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x1400053a0`
- `0x140007330`
- `0x140007430`
- `0x140007530`
- `0x140009600`
- `0x140009690`
- `0x140009b9c`
- `0x140009c44`
- `0x1400103d0`
- `0x140010ca0`
- `0x140029940`
- `0x140029cd0`
- `0x14002c010`
- `0x14002ea90`

## callees

- `0x140017190`

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
0x1400055cc  mov     r11, rsp
0x1400055cf  mov     [r11+20h], r9
0x1400055d3  sub     rsp, 48h
0x1400055d7  mov     rax, cs:pfnWppTraceMessage
0x1400055de  lea     r9, [r11+20h]
0x1400055e2  mov     qword ptr [r11-18h], 0
0x1400055ea  mov     qword ptr [r11-20h], 8
0x1400055f2  mov     [r11-28h], r9
0x1400055f6  movzx   r9d, dx
0x1400055fa  mov     edx, 2Bh ; '+'
0x1400055ff  call    _guard_dispatch_icall
0x140005604  add     rsp, 48h
0x140005608  retn
```
