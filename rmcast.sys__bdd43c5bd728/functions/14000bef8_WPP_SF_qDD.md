# WPP_SF_qDD

- ea: `0x14000bef8`
- end: `0x14000bf53`
- name: `WPP_SF_qDD`
- size: `91`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b0b0`
- `0x14000bf5c`
- `0x14001013c`
- `0x140014540`
- `0x140017300`

## callees

- `0x14001ce30`

## pseudocode

```c
__int64 WPP_SF_qDD(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
{
  __int64 v4; // [rsp+88h] [rbp+20h] BYREF
  va_list va; // [rsp+88h] [rbp+20h]
  __int64 v6; // [rsp+90h] [rbp+28h] BYREF
  va_list va1; // [rsp+90h] [rbp+28h]
  va_list va2; // [rsp+98h] [rbp+30h] BYREF

  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v4 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v6 = va_arg(va2, _QWORD);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           (__int64 *)va,
           8,
           (__int64 *)va1,
           4,
           va2,
           4,
           0);
}

```

## disassembly

```asm
0x14000bef8  mov     r11, rsp
0x14000befb  mov     [r11+20h], r9
0x14000beff  sub     rsp, 68h
0x14000bf03  mov     rax, cs:pfnWppTraceMessage
0x14000bf0a  lea     r9, [r11+30h]
0x14000bf0e  mov     qword ptr [r11-18h], 0
0x14000bf16  mov     r10d, 4
0x14000bf1c  mov     [r11-20h], r10
0x14000bf20  mov     [r11-28h], r9
0x14000bf24  lea     r9, [r11+28h]
0x14000bf28  mov     [r11-30h], r10
0x14000bf2c  mov     [r11-38h], r9
0x14000bf30  lea     r9, [r11+20h]
0x14000bf34  mov     qword ptr [r11-40h], 8
0x14000bf3c  mov     [r11-48h], r9
0x14000bf40  movzx   r9d, dx
0x14000bf44  lea     edx, [r10+27h]
0x14000bf48  call    _guard_dispatch_icall
0x14000bf4d  add     rsp, 68h
0x14000bf51  retn
```
