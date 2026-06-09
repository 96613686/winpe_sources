# WPP_SF_dddddd

- ea: `0x140015754`
- end: `0x1400157dd`
- name: `WPP_SF_dddddd`
- size: `137`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d414`
- `0x1400120b4`
- `0x140012efc`

## callees

- `0x14001ce30`

## pseudocode

```c
__int64 WPP_SF_dddddd(__int64 a1, unsigned __int16 a2, __int64 a3, int a4, ...)
{
  int v5; // [rsp+B8h] [rbp+20h] BYREF
  __int64 v6; // [rsp+C0h] [rbp+28h] BYREF
  va_list va; // [rsp+C0h] [rbp+28h]
  __int64 v8; // [rsp+C8h] [rbp+30h] BYREF
  va_list va1; // [rsp+C8h] [rbp+30h]
  __int64 v10; // [rsp+D0h] [rbp+38h] BYREF
  va_list va2; // [rsp+D0h] [rbp+38h]
  __int64 v12; // [rsp+D8h] [rbp+40h] BYREF
  va_list va3; // [rsp+D8h] [rbp+40h]
  va_list va4; // [rsp+E0h] [rbp+48h] BYREF

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
  v5 = a4;
  return ((__int64 (__fastcall *)(__int64, __int64, __int64 *, _QWORD, int *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
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
           (__int64 *)va3,
           4,
           va4,
           4,
           0);
}

```

## disassembly

```asm
0x140015754  mov     r11, rsp
0x140015757  mov     [r11+20h], r9d
0x14001575b  sub     rsp, 98h
0x140015762  mov     rax, cs:pfnWppTraceMessage
0x140015769  lea     r8, [r11+48h]
0x14001576d  mov     qword ptr [r11-18h], 0
0x140015775  mov     r9d, 4
0x14001577b  mov     [r11-20h], r9
0x14001577f  mov     [r11-28h], r8
0x140015783  lea     r8, [r11+40h]
0x140015787  mov     [r11-30h], r9
0x14001578b  mov     [r11-38h], r8
0x14001578f  lea     r8, [r11+38h]
0x140015793  mov     [r11-40h], r9
0x140015797  mov     [r11-48h], r8
0x14001579b  lea     r8, [r11+30h]
0x14001579f  mov     [r11-50h], r9
0x1400157a3  mov     [r11-58h], r8
0x1400157a7  lea     r8, [r11+28h]
0x1400157ab  mov     [r11-60h], r9
0x1400157af  mov     [r11-68h], r8
0x1400157b3  lea     r8, [r11+20h]
0x1400157b7  mov     [r11-70h], r9
0x1400157bb  mov     [r11-78h], r8
0x1400157bf  lea     r8, WPP_9481eaf791d131fecb736b68b85870ad_Traceguids
0x1400157c6  movzx   r9d, dx
0x1400157ca  mov     edx, 2Bh ; '+'
0x1400157cf  call    _guard_dispatch_icall
0x1400157d4  add     rsp, 98h
0x1400157db  retn
```
