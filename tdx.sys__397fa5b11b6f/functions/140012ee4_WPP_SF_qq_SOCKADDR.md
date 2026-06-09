# WPP_SF_qq_SOCKADDR_

- ea: `0x140012ee4`
- end: `0x140012f5e`
- name: `WPP_SF_qq_SOCKADDR_`
- size: `122`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140001ce0`
- `0x140006608`
- `0x140007b90`
- `0x140011cb4`

## callees

- `0x140018590`

## pseudocode

```c
__int64 WPP_SF_qq_SOCKADDR_(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
{
  __int64 v4; // [rsp+98h] [rbp+20h] BYREF
  va_list va; // [rsp+98h] [rbp+20h]
  __int64 v6; // [rsp+A0h] [rbp+28h] BYREF
  va_list va1; // [rsp+A0h] [rbp+28h]
  __int64 v8; // [rsp+A8h] [rbp+30h]
  va_list va2; // [rsp+B0h] [rbp+38h] BYREF

  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v4 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v6 = va_arg(va2, _QWORD);
  v8 = va_arg(va2, _QWORD);
  return pfnWppTraceMessage(
           a1,
           43,
           WPP_63c55c6b4ff2326ef703f60977e9aaef_Traceguids,
           a2,
           (__int64 *)va,
           8,
           (__int64 *)va1,
           8,
           v8 + 8,
           2,
           *(_QWORD *)v8,
           *(unsigned __int16 *)(v8 + 8),
           0);
}

```

## disassembly

```asm
0x140012ee4  mov     r11, rsp
0x140012ee7  mov     [r11+20h], r9
0x140012eeb  sub     rsp, 78h
0x140012eef  mov     r8, [rsp+78h+arg_28]
0x140012ef7  mov     qword ptr [r11-18h], 0
0x140012eff  lea     r9, [r8+8]
0x140012f03  mov     r8, [r8]
0x140012f06  movzx   eax, word ptr [r9]
0x140012f0a  mov     [r11-20h], rax
0x140012f0e  lea     rax, [r11+28h]
0x140012f12  mov     [r11-28h], r8
0x140012f16  mov     r8d, 8
0x140012f1c  mov     qword ptr [r11-30h], 2
0x140012f24  mov     [r11-38h], r9
0x140012f28  mov     [r11-40h], r8
0x140012f2c  mov     [r11-48h], rax
0x140012f30  lea     rax, [r11+20h]
0x140012f34  mov     [r11-50h], r8
0x140012f38  lea     r8, WPP_63c55c6b4ff2326ef703f60977e9aaef_Traceguids
0x140012f3f  mov     [r11-58h], rax
0x140012f43  mov     rax, cs:pfnWppTraceMessage
0x140012f4a  movzx   r9d, dx
0x140012f4e  mov     edx, 2Bh ; '+'
0x140012f53  call    _guard_dispatch_icall
0x140012f58  add     rsp, 78h
0x140012f5c  retn
```
