# WPP_SF__guid_iD

- ea: `0x14000fdc0`
- end: `0x14000fe16`
- name: `WPP_SF__guid_iD`
- size: `86`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x14000f158`
- `0x140011418`
- `0x14001152c`
- `0x140011920`
- `0x140011a2c`
- `0x14002df08`

## callees

- `0x140017190`

## pseudocode

```c
__int64 WPP_SF__guid_iD(__int64 a1, unsigned __int16 a2, __int64 a3, __int64 a4, ...)
{
  __int64 v5; // [rsp+90h] [rbp+28h] BYREF
  va_list va; // [rsp+90h] [rbp+28h]
  va_list va1; // [rsp+98h] [rbp+30h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v5 = va_arg(va1, _QWORD);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, __int64, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           a4,
           16,
           (__int64 *)va,
           8,
           va1,
           4,
           0);
}

```

## disassembly

```asm
0x14000fdc0  mov     r11, rsp
0x14000fdc3  sub     rsp, 68h
0x14000fdc7  mov     rax, cs:pfnWppTraceMessage
0x14000fdce  lea     r10, [r11+30h]
0x14000fdd2  mov     qword ptr [r11-18h], 0
0x14000fdda  mov     qword ptr [r11-20h], 4
0x14000fde2  mov     [r11-28h], r10
0x14000fde6  lea     r10, [r11+28h]
0x14000fdea  mov     qword ptr [r11-30h], 8
0x14000fdf2  mov     [r11-38h], r10
0x14000fdf6  mov     qword ptr [r11-40h], 10h
0x14000fdfe  mov     [r11-48h], r9
0x14000fe02  movzx   r9d, dx
0x14000fe06  mov     edx, 2Bh ; '+'
0x14000fe0b  call    _guard_dispatch_icall
0x14000fe10  add     rsp, 68h
0x14000fe14  retn
```
