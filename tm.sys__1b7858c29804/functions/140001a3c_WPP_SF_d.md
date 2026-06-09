# WPP_SF_d

- ea: `0x140001a3c`
- end: `0x140001a81`
- name: `WPP_SF_d`
- size: `69`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x14000e288`
- `0x14000e3c4`
- `0x14000e634`
- `0x14000e758`
- `0x14000ea5c`
- `0x14001a630`
- `0x14001ca60`
- `0x14001ec00`

## callees

- `0x1400025c0`

## pseudocode

```c
__int64 __fastcall WPP_SF_d(__int64 a1, unsigned __int16 a2, __int64 a3, int a4)
{
  int v5; // [rsp+68h] [rbp+20h] BYREF

  v5 = a4;
  return ((__int64 (__fastcall *)(__int64, __int64, __int64 *, _QWORD, int *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           WPP_b60b885ff4cd344d6813b01a736c9140_Traceguids,
           a2,
           &v5,
           4,
           0);
}

```

## disassembly

```asm
0x140001a3c  mov     r11, rsp
0x140001a3f  mov     [r11+20h], r9d
0x140001a43  sub     rsp, 48h
0x140001a47  mov     rax, cs:pfnWppTraceMessage
0x140001a4e  lea     r8, [r11+20h]
0x140001a52  mov     qword ptr [r11-18h], 0
0x140001a5a  mov     qword ptr [r11-20h], 4
0x140001a62  mov     [r11-28h], r8
0x140001a66  lea     r8, WPP_b60b885ff4cd344d6813b01a736c9140_Traceguids
0x140001a6d  movzx   r9d, dx
0x140001a71  mov     edx, 2Bh ; '+'
0x140001a76  call    _guard_dispatch_icall
0x140001a7b  add     rsp, 48h
0x140001a7f  retn
```
