# WPP_SF_qd

- ea: `0x14000ed88`
- end: `0x14000eddd`
- name: `WPP_SF_qd`
- size: `85`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000745c`
- `0x14000ea3c`

## callees

- `0x14000f150`

## pseudocode

```c
__int64 WPP_SF_qd(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
{
  __int64 v4; // [rsp+78h] [rbp+20h] BYREF
  va_list va; // [rsp+78h] [rbp+20h]
  va_list va1; // [rsp+80h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v4 = va_arg(va1, _QWORD);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64 *, _QWORD, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           WPP_63d282d22d9e3f2cd53cfde58a2ac431_Traceguids,
           a2,
           (__int64 *)va,
           8,
           va1,
           4,
           0);
}

```

## disassembly

```asm
0x14000ed88  mov     r11, rsp
0x14000ed8b  mov     [r11+20h], r9
0x14000ed8f  sub     rsp, 58h
0x14000ed93  mov     rax, cs:pfnWppTraceMessage
0x14000ed9a  lea     r8, [r11+28h]
0x14000ed9e  mov     qword ptr [r11-18h], 0
0x14000eda6  mov     qword ptr [r11-20h], 4
0x14000edae  mov     [r11-28h], r8
0x14000edb2  lea     r8, [r11+20h]
0x14000edb6  mov     qword ptr [r11-30h], 8
0x14000edbe  mov     [r11-38h], r8
0x14000edc2  lea     r8, WPP_63d282d22d9e3f2cd53cfde58a2ac431_Traceguids
0x14000edc9  movzx   r9d, dx
0x14000edcd  mov     edx, 2Bh ; '+'
0x14000edd2  call    _guard_dispatch_icall
0x14000edd7  add     rsp, 58h
0x14000eddb  retn
```
