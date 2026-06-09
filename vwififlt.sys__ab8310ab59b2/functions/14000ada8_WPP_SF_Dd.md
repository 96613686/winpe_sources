# WPP_SF_Dd

- ea: `0x14000ada8`
- end: `0x14000adfb`
- name: `WPP_SF_Dd`
- size: `83`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x14000204c`
- `0x140004568`
- `0x1400080f0`
- `0x1400087b0`
- `0x140008e70`
- `0x140009300`
- `0x1400097e4`
- `0x140009bec`
- `0x140009e70`
- `0x14000a880`
- `0x14000ab50`
- `0x14000aef0`

## callees

- `0x14000f150`

## pseudocode

```c
__int64 WPP_SF_Dd(__int64 a1, unsigned __int16 a2, __int64 a3, int a4, ...)
{
  int v5; // [rsp+78h] [rbp+20h] BYREF
  va_list va; // [rsp+80h] [rbp+28h] BYREF

  va_start(va, a4);
  v5 = a4;
  return ((__int64 (__fastcall *)(__int64, __int64, __int64 *, _QWORD, int *, __int64, __int64 *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids,
           a2,
           &v5,
           4,
           (__int64 *)va,
           4,
           0);
}

```

## disassembly

```asm
0x14000ada8  mov     r11, rsp
0x14000adab  mov     [r11+20h], r9d
0x14000adaf  sub     rsp, 58h
0x14000adb3  mov     rax, cs:pfnWppTraceMessage
0x14000adba  lea     r8, [r11+28h]
0x14000adbe  mov     qword ptr [r11-18h], 0
0x14000adc6  mov     r9d, 4
0x14000adcc  mov     [r11-20h], r9
0x14000add0  mov     [r11-28h], r8
0x14000add4  lea     r8, [r11+20h]
0x14000add8  mov     [r11-30h], r9
0x14000addc  mov     [r11-38h], r8
0x14000ade0  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x14000ade7  movzx   r9d, dx
0x14000adeb  mov     edx, 2Bh ; '+'
0x14000adf0  call    _guard_dispatch_icall
0x14000adf5  add     rsp, 58h
0x14000adf9  retn
```
