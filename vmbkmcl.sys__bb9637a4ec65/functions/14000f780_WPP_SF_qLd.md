# WPP_SF_qLd

- ea: `0x14000f780`
- end: `0x14000f7e3`
- name: `WPP_SF_qLd`
- size: `99`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b3d8`
- `0x14000c87c`
- `0x14000cdb0`
- `0x14000e148`
- `0x14000ed00`
- `0x14000f340`

## callees

- `0x140011ed0`

## pseudocode

```c
__int64 WPP_SF_qLd(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
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
  return ((__int64 (__fastcall *)(__int64, __int64, __int64 *, _QWORD, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           WPP_fa014546bb113ca58de70d4b381949e7_Traceguids,
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
0x14000f780  mov     r11, rsp
0x14000f783  mov     [r11+20h], r9
0x14000f787  sub     rsp, 68h
0x14000f78b  mov     rax, cs:pfnWppTraceMessage
0x14000f792  lea     r8, [r11+30h]
0x14000f796  mov     qword ptr [r11-18h], 0
0x14000f79e  mov     r9d, 4
0x14000f7a4  mov     [r11-20h], r9
0x14000f7a8  mov     [r11-28h], r8
0x14000f7ac  lea     r8, [r11+28h]
0x14000f7b0  mov     [r11-30h], r9
0x14000f7b4  mov     [r11-38h], r8
0x14000f7b8  lea     r8, [r11+20h]
0x14000f7bc  mov     qword ptr [r11-40h], 8
0x14000f7c4  mov     [r11-48h], r8
0x14000f7c8  lea     r8, WPP_fa014546bb113ca58de70d4b381949e7_Traceguids
0x14000f7cf  movzx   r9d, dx
0x14000f7d3  mov     edx, 2Bh ; '+'
0x14000f7d8  call    _guard_dispatch_icall
0x14000f7dd  add     rsp, 68h
0x14000f7e1  retn
```
