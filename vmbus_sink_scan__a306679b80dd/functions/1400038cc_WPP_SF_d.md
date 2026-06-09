# WPP_SF_d

- ea: `0x1400038cc`
- end: `0x14000390a`
- name: `WPP_SF_d`
- size: `62`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `27`
- callee_count: `1`
- tags: ``

## callers

- `0x140003eb8`
- `0x140005aa0`
- `0x140005bf0`
- `0x1400063d0`
- `0x140006ca0`
- `0x14000bbec`
- `0x14000edc4`
- `0x14000ef68`
- `0x140012f34`
- `0x1400131f0`
- `0x1400132a8`
- `0x140013408`
- `0x140013a24`
- `0x140013e08`
- `0x140027fe4`
- `0x14002841c`
- `0x140029390`
- `0x140029f18`
- `0x14002a530`
- `0x14002a5c0`
- `0x14002a740`
- `0x14002b2a0`
- `0x14002b7e0`
- `0x14002b890`
- `0x14002e06c`
- `0x14002e6b0`
- `0x14003003c`

## callees

- `0x140017190`

## pseudocode

```c
__int64 __fastcall WPP_SF_d(__int64 a1, unsigned __int16 a2, __int64 a3, int a4)
{
  int v5; // [rsp+68h] [rbp+20h] BYREF

  v5 = a4;
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, int *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           &v5,
           4,
           0);
}

```

## disassembly

```asm
0x1400038cc  mov     r11, rsp
0x1400038cf  mov     [r11+20h], r9d
0x1400038d3  sub     rsp, 48h
0x1400038d7  mov     rax, cs:pfnWppTraceMessage
0x1400038de  lea     r9, [r11+20h]
0x1400038e2  mov     qword ptr [r11-18h], 0
0x1400038ea  mov     qword ptr [r11-20h], 4
0x1400038f2  mov     [r11-28h], r9
0x1400038f6  movzx   r9d, dx
0x1400038fa  mov     edx, 2Bh ; '+'
0x1400038ff  call    _guard_dispatch_icall
0x140003904  add     rsp, 48h
0x140003908  retn
```
