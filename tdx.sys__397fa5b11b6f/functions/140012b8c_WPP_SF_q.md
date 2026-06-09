# WPP_SF_q

- ea: `0x140012b8c`
- end: `0x140012bca`
- name: `WPP_SF_q`
- size: `62`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x140001550`
- `0x140003c9c`
- `0x1400054ec`
- `0x140006b40`
- `0x140007b90`
- `0x1400087a0`
- `0x14000a040`
- `0x14000b330`
- `0x14000bab0`
- `0x14000cfc0`
- `0x14000f0fc`

## callees

- `0x140018590`

## pseudocode

```c
__int64 WPP_SF_q(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
{
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, __int64 *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           (__int64 *)va,
           8,
           0);
}

```

## disassembly

```asm
0x140012b8c  mov     r11, rsp
0x140012b8f  mov     [r11+20h], r9
0x140012b93  sub     rsp, 48h
0x140012b97  mov     rax, cs:pfnWppTraceMessage
0x140012b9e  lea     r9, [r11+20h]
0x140012ba2  mov     qword ptr [r11-18h], 0
0x140012baa  mov     qword ptr [r11-20h], 8
0x140012bb2  mov     [r11-28h], r9
0x140012bb6  movzx   r9d, dx
0x140012bba  mov     edx, 2Bh ; '+'
0x140012bbf  call    _guard_dispatch_icall
0x140012bc4  add     rsp, 48h
0x140012bc8  retn
```
