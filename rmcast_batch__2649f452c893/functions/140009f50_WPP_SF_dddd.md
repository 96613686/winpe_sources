# WPP_SF_dddd

- ea: `0x140009f50`
- end: `0x140009fb3`
- name: `WPP_SF_dddd`
- size: `99`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x140009630`
- `0x14000ca08`
- `0x14000e03c`
- `0x14000ec50`
- `0x14000f2d8`
- `0x140013d90`
- `0x140014540`
- `0x140019424`
- `0x14001a6d0`

## callees

- `0x14001ce30`

## pseudocode

```c
__int64 WPP_SF_dddd(__int64 a1, unsigned __int16 a2, __int64 a3, int a4, ...)
{
  int v5; // [rsp+98h] [rbp+20h] BYREF
  __int64 v6; // [rsp+A0h] [rbp+28h] BYREF
  va_list va; // [rsp+A0h] [rbp+28h]
  __int64 v8; // [rsp+A8h] [rbp+30h] BYREF
  va_list va1; // [rsp+A8h] [rbp+30h]
  va_list va2; // [rsp+B0h] [rbp+38h] BYREF

  va_start(va2, a4);
  va_start(va1, a4);
  va_start(va, a4);
  v6 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v8 = va_arg(va2, _QWORD);
  v5 = a4;
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, int *, __int64, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           &v5,
           4,
           (__int64 *)va,
           4,
           (__int64 *)va1,
           4,
           va2,
           4,
           0);
}

```

## disassembly

```asm
0x140009f50  mov     r11, rsp
0x140009f53  mov     [r11+20h], r9d
0x140009f57  sub     rsp, 78h
0x140009f5b  mov     rax, cs:pfnWppTraceMessage
0x140009f62  lea     r9, [r11+38h]
0x140009f66  mov     qword ptr [r11-18h], 0
0x140009f6e  mov     r10d, 4
0x140009f74  mov     [r11-20h], r10
0x140009f78  mov     [r11-28h], r9
0x140009f7c  lea     r9, [r11+30h]
0x140009f80  mov     [r11-30h], r10
0x140009f84  mov     [r11-38h], r9
0x140009f88  lea     r9, [r11+28h]
0x140009f8c  mov     [r11-40h], r10
0x140009f90  mov     [r11-48h], r9
0x140009f94  lea     r9, [r11+20h]
0x140009f98  mov     [r11-50h], r10
0x140009f9c  mov     [r11-58h], r9
0x140009fa0  movzx   r9d, dx
0x140009fa4  lea     edx, [r10+27h]
0x140009fa8  call    _guard_dispatch_icall
0x140009fad  add     rsp, 78h
0x140009fb1  retn
```
