# WPP_SF_ddddddd

- ea: `0x1400157e4`
- end: `0x140015872`
- name: `WPP_SF_ddddddd`
- size: `142`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD)`
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
__int64 __fastcall WPP_SF_ddddddd(
        __int64 a1,
        unsigned __int16 a2,
        __int64 a3,
        int a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10)
{
  int v11; // [rsp+C8h] [rbp+20h] BYREF

  v11 = a4;
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, int *, __int64, int *, __int64, int *, __int64, int *, __int64, int *, __int64, int *, __int64, int *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           &v11,
           4,
           &a5,
           4,
           &a6,
           4,
           &a7,
           4,
           &a8,
           4,
           &a9,
           4,
           &a10,
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
