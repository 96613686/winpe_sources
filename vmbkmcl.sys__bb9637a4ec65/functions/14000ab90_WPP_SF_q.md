# WPP_SF_q

- ea: `0x14000ab90`
- end: `0x14000abce`
- name: `WPP_SF_q`
- size: `62`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x14000a940`
- `0x14000afe8`
- `0x14000b3d8`
- `0x14000bb70`
- `0x14000cbc8`
- `0x14000cdb0`
- `0x14000d310`
- `0x14000d83c`
- `0x14000d9b0`
- `0x14000defc`
- `0x14000e9e0`
- `0x14000ed00`
- `0x14001c758`
- `0x14001cdd4`
- `0x14001d4f0`

## callees

- `0x140011ed0`

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
0x14000ab90  mov     r11, rsp
0x14000ab93  mov     [r11+20h], r9
0x14000ab97  sub     rsp, 48h
0x14000ab9b  mov     rax, cs:pfnWppTraceMessage
0x14000aba2  lea     r9, [r11+20h]
0x14000aba6  mov     qword ptr [r11-18h], 0
0x14000abae  mov     qword ptr [r11-20h], 8
0x14000abb6  mov     [r11-28h], r9
0x14000abba  movzx   r9d, dx
0x14000abbe  mov     edx, 2Bh ; '+'
0x14000abc3  call    _guard_dispatch_icall
0x14000abc8  add     rsp, 48h
0x14000abcc  retn
```
