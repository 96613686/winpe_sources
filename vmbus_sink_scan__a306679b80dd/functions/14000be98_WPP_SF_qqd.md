# WPP_SF_qqd

- ea: `0x14000be98`
- end: `0x14000befb`
- name: `WPP_SF_qqd`
- size: `99`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b4f0`
- `0x14000b800`
- `0x14000ba60`
- `0x14000bb40`

## callees

- `0x140017190`

## pseudocode

```c
__int64 __fastcall WPP_SF_qqd(__int64 a1, unsigned __int16 a2, __int64 a3, __int64 a4, __int64 a5, int a6)
{
  __int64 v7; // [rsp+88h] [rbp+20h] BYREF

  v7 = a4;
  return ((__int64 (__fastcall *)(__int64, __int64, __int64 *, _QWORD, __int64 *, __int64, __int64 *, __int64, int *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           WPP_b7e7155a638734823fba4b93e4cd9774_Traceguids,
           a2,
           &v7,
           8,
           &a5,
           8,
           &a6,
           4,
           0);
}

```

## disassembly

```asm
0x14000be98  mov     r11, rsp
0x14000be9b  mov     [r11+20h], r9
0x14000be9f  sub     rsp, 68h
0x14000bea3  mov     rax, cs:pfnWppTraceMessage
0x14000beaa  lea     r8, [r11+30h]
0x14000beae  mov     qword ptr [r11-18h], 0
0x14000beb6  mov     r9d, 8
0x14000bebc  mov     qword ptr [r11-20h], 4
0x14000bec4  mov     [r11-28h], r8
0x14000bec8  lea     r8, [r11+28h]
0x14000becc  mov     [r11-30h], r9
0x14000bed0  mov     [r11-38h], r8
0x14000bed4  lea     r8, [r11+20h]
0x14000bed8  mov     [r11-40h], r9
0x14000bedc  mov     [r11-48h], r8
0x14000bee0  lea     r8, WPP_b7e7155a638734823fba4b93e4cd9774_Traceguids
0x14000bee7  movzx   r9d, dx
0x14000beeb  mov     edx, 2Bh ; '+'
0x14000bef0  call    _guard_dispatch_icall
0x14000bef5  add     rsp, 68h
0x14000bef9  retn
```
