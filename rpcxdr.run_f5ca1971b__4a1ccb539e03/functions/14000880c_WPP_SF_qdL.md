# WPP_SF_qdL

- ea: `0x14000880c`
- end: `0x14000886f`
- name: `WPP_SF_qdL`
- size: `99`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1400070c4`
- `0x140007640`
- `0x140007d58`
- `0x1400082a8`
- `0x1400083b8`

## callees

- `0x140015680`

## pseudocode

```c
__int64 WPP_SF_qdL(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
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
           WPP_cd42a1555dae3c8c93cac586485c41cc_Traceguids,
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
0x14000880c  mov     r11, rsp
0x14000880f  mov     [r11+20h], r9
0x140008813  sub     rsp, 68h
0x140008817  mov     rax, cs:pfnWppTraceMessage
0x14000881e  lea     r8, [r11+30h]
0x140008822  mov     qword ptr [r11-18h], 0
0x14000882a  mov     r9d, 4
0x140008830  mov     [r11-20h], r9
0x140008834  mov     [r11-28h], r8
0x140008838  lea     r8, [r11+28h]
0x14000883c  mov     [r11-30h], r9
0x140008840  mov     [r11-38h], r8
0x140008844  lea     r8, [r11+20h]
0x140008848  mov     qword ptr [r11-40h], 8
0x140008850  mov     [r11-48h], r8
0x140008854  lea     r8, WPP_cd42a1555dae3c8c93cac586485c41cc_Traceguids
0x14000885b  movzx   r9d, dx
0x14000885f  mov     edx, 2Bh ; '+'
0x140008864  call    _guard_dispatch_icall
0x140008869  add     rsp, 68h
0x14000886d  retn
```
