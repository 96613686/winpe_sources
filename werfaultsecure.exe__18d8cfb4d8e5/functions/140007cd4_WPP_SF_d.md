# WPP_SF_d

- ea: `0x140007cd4`
- end: `0x140007d0b`
- name: `WPP_SF_d`
- size: `55`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140007634`
- `0x140007a4c`
- `0x14000e8c4`
- `0x14000f334`
- `0x14000f81c`
- `0x14000fb3c`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x140007d00`
- `ntdll!EtwTraceMessage` at `0x140007d00`

## pseudocode

```c
__int64 __fastcall WPP_SF_d(__int64 a1, unsigned __int16 a2, __int64 a3, int a4)
{
  int v5; // [rsp+68h] [rbp+20h] BYREF

  v5 = a4;
  return EtwTraceMessage(a1, 43, a3, a2, &v5, 4, 0);
}

```

## disassembly

```asm
0x140007cd4  mov     r11, rsp
0x140007cd7  mov     [r11+20h], r9d
0x140007cdb  sub     rsp, 48h
0x140007cdf  mov     qword ptr [r11-18h], 0
0x140007ce7  lea     rax, [r11+20h]
0x140007ceb  movzx   r9d, dx
0x140007cef  mov     edx, 2Bh ; '+'
0x140007cf4  mov     qword ptr [r11-20h], 4
0x140007cfc  mov     [r11-28h], rax
0x140007d00  call    cs:__imp_EtwTraceMessage
0x140007d06  add     rsp, 48h
0x140007d0a  retn
```
