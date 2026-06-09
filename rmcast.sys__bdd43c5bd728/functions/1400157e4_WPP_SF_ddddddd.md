# WPP_SF_ddddddd

- ea: `0x1400157e4`
- end: `0x140015872`
- name: `WPP_SF_ddddddd`
- size: `142`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400120b4`
- `0x140012efc`
- `0x140017c80`

## callees

- `0x14001ce30`

## pseudocode

```c
__int64 WPP_SF_ddddddd(__int64 a1, unsigned __int16 a2, __int64 a3, int a4, ...)
{
  int v5; // [rsp+C8h] [rbp+20h] BYREF
  __int64 v6; // [rsp+D0h] [rbp+28h] BYREF
  va_list va; // [rsp+D0h] [rbp+28h]
  __int64 v8; // [rsp+D8h] [rbp+30h] BYREF
  va_list va1; // [rsp+D8h] [rbp+30h]
  __int64 v10; // [rsp+E0h] [rbp+38h] BYREF
  va_list va2; // [rsp+E0h] [rbp+38h]
  __int64 v12; // [rsp+E8h] [rbp+40h] BYREF
  va_list va3; // [rsp+E8h] [rbp+40h]
  __int64 v14; // [rsp+F0h] [rbp+48h] BYREF
  va_list va4; // [rsp+F0h] [rbp+48h]
  va_list va5; // [rsp+F8h] [rbp+50h] BYREF

  va_start(va5, a4);
  va_start(va4, a4);
  va_start(va3, a4);
  va_start(va2, a4);
  va_start(va1, a4);
  va_start(va, a4);
  v6 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v8 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v10 = va_arg(va3, _QWORD);
  va_copy(va4, va3);
  v12 = va_arg(va4, _QWORD);
  va_copy(va5, va4);
  v14 = va_arg(va5, _QWORD);
  v5 = a4;
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, int *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
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
           (__int64 *)va2,
           4,
           (__int64 *)va3,
           4,
           (__int64 *)va4,
           4,
           va5,
           4,
           0);
}

```

## disassembly

```asm
0x1400157e4  mov     r11, rsp
0x1400157e7  mov     [r11+20h], r9d
0x1400157eb  sub     rsp, 0A8h
0x1400157f2  mov     rax, cs:pfnWppTraceMessage
0x1400157f9  lea     r9, [r11+50h]
0x1400157fd  mov     qword ptr [r11-18h], 0
0x140015805  mov     r10d, 4
0x14001580b  mov     [r11-20h], r10
0x14001580f  mov     [r11-28h], r9
0x140015813  lea     r9, [r11+48h]
0x140015817  mov     [r11-30h], r10
0x14001581b  mov     [r11-38h], r9
0x14001581f  lea     r9, [r11+40h]
0x140015823  mov     [r11-40h], r10
0x140015827  mov     [r11-48h], r9
0x14001582b  lea     r9, [r11+38h]
0x14001582f  mov     [r11-50h], r10
0x140015833  mov     [r11-58h], r9
0x140015837  lea     r9, [r11+30h]
0x14001583b  mov     [r11-60h], r10
0x14001583f  mov     [r11-68h], r9
0x140015843  lea     r9, [r11+28h]
0x140015847  mov     [r11-70h], r10
0x14001584b  mov     [r11-78h], r9
0x14001584f  lea     r9, [r11+20h]
0x140015853  mov     [r11-80h], r10
0x140015857  mov     [rsp+0A8h+var_88], r9
0x14001585c  movzx   r9d, dx
0x140015860  lea     edx, [r10+27h]
0x140015864  call    _guard_dispatch_icall
0x140015869  add     rsp, 0A8h
0x140015870  retn
```
