# WPP_SF_ddD

- ea: `0x14000dc58`
- end: `0x14000dcb7`
- name: `WPP_SF_ddD`
- size: `95`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140008e70`
- `0x140009300`

## callees

- `0x14000f150`

## pseudocode

```c
__int64 WPP_SF_ddD(__int64 a1, unsigned __int16 a2, __int64 a3, int a4, ...)
{
  int v5; // [rsp+88h] [rbp+20h] BYREF
  __int64 v6; // [rsp+90h] [rbp+28h] BYREF
  va_list va; // [rsp+90h] [rbp+28h]
  va_list va1; // [rsp+98h] [rbp+30h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v6 = va_arg(va1, _QWORD);
  v5 = a4;
  return pfnWppTraceMessage(
           a1,
           43,
           WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids,
           a2,
           &v5,
           4,
           (__int64 *)va,
           4,
           va1,
           4,
           0);
}

```

## disassembly

```asm
0x14000dc58  mov     r11, rsp
0x14000dc5b  mov     [r11+20h], r9d
0x14000dc5f  sub     rsp, 68h
0x14000dc63  mov     rax, cs:pfnWppTraceMessage
0x14000dc6a  lea     r8, [r11+30h]
0x14000dc6e  mov     qword ptr [r11-18h], 0
0x14000dc76  mov     r9d, 4
0x14000dc7c  mov     [r11-20h], r9
0x14000dc80  mov     [r11-28h], r8
0x14000dc84  lea     r8, [r11+28h]
0x14000dc88  mov     [r11-30h], r9
0x14000dc8c  mov     [r11-38h], r8
0x14000dc90  lea     r8, [r11+20h]
0x14000dc94  mov     [r11-40h], r9
0x14000dc98  mov     [r11-48h], r8
0x14000dc9c  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x14000dca3  movzx   r9d, dx
0x14000dca7  mov     edx, 2Bh ; '+'
0x14000dcac  call    _guard_dispatch_icall
0x14000dcb1  add     rsp, 68h
0x14000dcb5  retn
```
