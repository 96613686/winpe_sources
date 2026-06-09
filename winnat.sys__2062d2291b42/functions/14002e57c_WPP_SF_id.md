# WPP_SF_id

- ea: `0x14002e57c`
- end: `0x14002e5c5`
- name: `WPP_SF_id`
- size: `73`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
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
void WPP_SF_id(__int64 a1, USHORT a2, __int64 a3, ...)
{
  __int64 v3; // [rsp+68h] [rbp+20h] BYREF
  va_list va; // [rsp+68h] [rbp+20h]
  va_list va1; // [rsp+70h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v3 = va_arg(va1, _QWORD);
  FastWppTraceMessage(1025, a2, (ULONGLONG)WPP_00475dad78ff34078f24129d9bdcf001_Traceguids, va, 8, va1, 4, 0);
}

```

## disassembly

```asm
0x14002e57c  mov     r11, rsp
0x14002e57f  mov     [r11+20h], r9
0x14002e583  sub     rsp, 48h
0x14002e587  mov     qword ptr [r11-10h], 0
0x14002e58f  lea     rax, [r11+28h]
0x14002e593  mov     qword ptr [r11-18h], 4
0x14002e59b  lea     r9, [r11+20h]
0x14002e59f  mov     [r11-20h], rax
0x14002e5a3  lea     r8, WPP_00475dad78ff34078f24129d9bdcf001_Traceguids
0x14002e5aa  mov     ecx, 401h
0x14002e5af  movzx   edx, dx
0x14002e5b2  mov     qword ptr [r11-28h], 8
0x14002e5ba  call    FastWppTraceMessage
0x14002e5bf  add     rsp, 48h
0x14002e5c3  retn
```
