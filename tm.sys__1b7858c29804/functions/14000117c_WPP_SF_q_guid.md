# WPP_SF_q_guid_

- ea: `0x14000117c`
- end: `0x1400011d5`
- name: `WPP_SF_q_guid_`
- size: `89`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x14000c010`
- `0x140010c70`
- `0x140011c80`
- `0x14001a2e0`
- `0x14001b594`
- `0x140020dd4`

## callees

- `0x1400025c0`

## pseudocode

```c
__int64 WPP_SF_q_guid_(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
{
  __int64 v4; // [rsp+78h] [rbp+20h] BYREF
  va_list va; // [rsp+78h] [rbp+20h]
  __int64 v6; // [rsp+80h] [rbp+28h]
  va_list va1; // [rsp+88h] [rbp+30h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v4 = va_arg(va1, _QWORD);
  v6 = va_arg(va1, _QWORD);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64 *, _QWORD, __int64 *, __int64, __int64, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           WPP_49ed135d36c7359d33070dea67dc05c0_Traceguids,
           a2,
           (__int64 *)va,
           8,
           v6,
           16,
           0);
}

```

## disassembly

```asm
0x14000117c  mov     r11, rsp
0x14000117f  mov     [r11+20h], r9
0x140001183  sub     rsp, 58h
0x140001187  mov     r8, [rsp+58h+arg_20]
0x14000118f  mov     rax, cs:pfnWppTraceMessage
0x140001196  mov     qword ptr [r11-18h], 0
0x14000119e  mov     qword ptr [r11-20h], 10h
0x1400011a6  mov     [r11-28h], r8
0x1400011aa  lea     r8, [r11+20h]
0x1400011ae  mov     qword ptr [r11-30h], 8
0x1400011b6  mov     [r11-38h], r8
0x1400011ba  lea     r8, WPP_49ed135d36c7359d33070dea67dc05c0_Traceguids
0x1400011c1  movzx   r9d, dx
0x1400011c5  mov     edx, 2Bh ; '+'
0x1400011ca  call    _guard_dispatch_icall
0x1400011cf  add     rsp, 58h
0x1400011d3  retn
```
