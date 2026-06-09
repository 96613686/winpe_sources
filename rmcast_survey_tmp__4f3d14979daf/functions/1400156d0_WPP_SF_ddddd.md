# WPP_SF_ddddd

- ea: `0x1400156d0`
- end: `0x14001574d`
- name: `WPP_SF_ddddd`
- size: `125`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14000c624`
- `0x14000d414`
- `0x14000e03c`
- `0x14000f2d8`
- `0x14000fe74`
- `0x14001013c`
- `0x140012efc`

## callees

- `0x14001ce30`

## pseudocode

```c
__int64 WPP_SF_ddddd(__int64 a1, unsigned __int16 a2, __int64 a3, int a4, ...)
{
  int v5; // [rsp+A8h] [rbp+20h] BYREF
  __int64 v6; // [rsp+B0h] [rbp+28h] BYREF
  va_list va; // [rsp+B0h] [rbp+28h]
  __int64 v8; // [rsp+B8h] [rbp+30h] BYREF
  va_list va1; // [rsp+B8h] [rbp+30h]
  __int64 v10; // [rsp+C0h] [rbp+38h] BYREF
  va_list va2; // [rsp+C0h] [rbp+38h]
  va_list va3; // [rsp+C8h] [rbp+40h] BYREF

  va_start(va3, a4);
  va_start(va2, a4);
  va_start(va1, a4);
  va_start(va, a4);
  v6 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v8 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v10 = va_arg(va3, _QWORD);
  v5 = a4;
  return ((__int64 (__fastcall *)(__int64, __int64, __int64 *, _QWORD, int *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           WPP_9481eaf791d131fecb736b68b85870ad_Traceguids,
           a2,
           &v5,
           4,
           (__int64 *)va,
           4,
           (__int64 *)va1,
           4,
           (__int64 *)va2,
           4,
           va3,
           4,
           0);
}

```

## disassembly

```asm
0x1400156d0  mov     r11, rsp
0x1400156d3  mov     [r11+20h], r9d
0x1400156d7  sub     rsp, 88h
0x1400156de  mov     rax, cs:pfnWppTraceMessage
0x1400156e5  lea     r8, [r11+40h]
0x1400156e9  mov     qword ptr [r11-18h], 0
0x1400156f1  mov     r9d, 4
0x1400156f7  mov     [r11-20h], r9
0x1400156fb  mov     [r11-28h], r8
0x1400156ff  lea     r8, [r11+38h]
0x140015703  mov     [r11-30h], r9
0x140015707  mov     [r11-38h], r8
0x14001570b  lea     r8, [r11+30h]
0x14001570f  mov     [r11-40h], r9
0x140015713  mov     [r11-48h], r8
0x140015717  lea     r8, [r11+28h]
0x14001571b  mov     [r11-50h], r9
0x14001571f  mov     [r11-58h], r8
0x140015723  lea     r8, [r11+20h]
0x140015727  mov     [r11-60h], r9
0x14001572b  mov     [r11-68h], r8
0x14001572f  lea     r8, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids
0x140015736  movzx   r9d, dx
0x14001573a  mov     edx, 2Bh ; '+'
0x14001573f  call    _guard_dispatch_icall
0x140015744  add     rsp, 88h
0x14001574b  retn
```
