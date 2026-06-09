# WPP_SF_qd

- ea: `0x14000f5c4`
- end: `0x14000f619`
- name: `WPP_SF_qd`
- size: `85`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x14000afe8`
- `0x14000b3d8`
- `0x14000bb70`
- `0x14000cfe4`
- `0x14000d310`
- `0x14000d9b0`
- `0x14000defc`
- `0x14000e4e0`
- `0x14000e9e0`
- `0x14000ed00`
- `0x14000f2b0`
- `0x14000f340`
- `0x14001c758`
- `0x14001cdd4`

## callees

- `0x140011ed0`

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
           WPP_fa014546bb113ca58de70d4b381949e7_Traceguids,
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
0x14000f5c4  mov     r11, rsp
0x14000f5c7  mov     [r11+20h], r9
0x14000f5cb  sub     rsp, 58h
0x14000f5cf  mov     rax, cs:pfnWppTraceMessage
0x14000f5d6  lea     r8, [r11+28h]
0x14000f5da  mov     qword ptr [r11-18h], 0
0x14000f5e2  mov     qword ptr [r11-20h], 4
0x14000f5ea  mov     [r11-28h], r8
0x14000f5ee  lea     r8, [r11+20h]
0x14000f5f2  mov     qword ptr [r11-30h], 8
0x14000f5fa  mov     [r11-38h], r8
0x14000f5fe  lea     r8, WPP_fa014546bb113ca58de70d4b381949e7_Traceguids
0x14000f605  movzx   r9d, dx
0x14000f609  mov     edx, 2Bh ; '+'
0x14000f60e  call    _guard_dispatch_icall
0x14000f613  add     rsp, 58h
0x14000f617  retn
```
