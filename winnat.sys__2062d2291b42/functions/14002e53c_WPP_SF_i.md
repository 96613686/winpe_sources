# WPP_SF_i

- ea: `0x14002e53c`
- end: `0x14002e575`
- name: `WPP_SF_i`
- size: `57`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1400164a8`
- `0x140016760`
- `0x1400169e4`
- `0x140016af0`
- `0x140034990`
- `0x140034a60`

## callees

- `0x1400188e8`

## pseudocode

```c
void WPP_SF_i(__int64 a1, USHORT a2, __int64 a3, ...)
{
  va_list va; // [rsp+58h] [rbp+20h] BYREF

  va_start(va, a3);
  FastWppTraceMessage(1025, a2, (ULONGLONG)WPP_00475dad78ff34078f24129d9bdcf001_Traceguids, va, 8, 0);
}

```

## disassembly

```asm
0x14002e53c  mov     rax, rsp
0x14002e53f  mov     [rax+20h], r9
0x14002e543  sub     rsp, 38h
0x14002e547  mov     qword ptr [rax-10h], 0
0x14002e54f  lea     r9, [rax+20h]
0x14002e553  mov     ecx, 401h
0x14002e558  movzx   edx, dx
0x14002e55b  lea     r8, WPP_00475dad78ff34078f24129d9bdcf001_Traceguids
0x14002e562  mov     qword ptr [rax-18h], 8
0x14002e56a  call    FastWppTraceMessage
0x14002e56f  add     rsp, 38h
0x14002e573  retn
```
